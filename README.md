# Trabalho-2---Documenta-o-de-Projeto-de-Software

# Documentação de Projeto: ShieldFolio


**Versão:** 1.2  
**Autora:** Giovanna Lima Torres Guasch  
**Data:** 13/11/2025  
*Projeto de sistema elaborado como parte da disciplina Projeto de Software.*

## 1. Introdução


[cite_start]Este documento reúne duas etapas principais: (1) a criação e revisão dos modelos de domínio e (2) o desenvolvimento dos modelos de projeto do sistema ShieldFolio[cite: 42].

[cite_start]Artistas digitais enfrentam hoje grandes dificuldades ao divulgar seus trabalhos na internet, principalmente no que diz respeito à proteção contra o uso indevido por ferramentas de Inteligência Artificial[cite: 43]. [cite_start]A maioria das plataformas de portfólio não dispõe de recursos eficientes de segurança ou controle de privacidade, o que torna as imagens suscetíveis a cópias, reutilizações ou extrações por modelos de IA generativa[cite: 44].

[cite_start]O ShieldFolio propõe-se a ser uma plataforma web voltada à exibição e ao gerenciamento de portfólios artísticos, priorizando a proteção das imagens e a organização personalizada[cite: 45].

## 2. Modelos de Usuário e Requisitos


### 2.1 Descrição de Atores


* **Artista:** É o principal usuário do sistema. Pode criar uma conta, enviar imagens com proteção contra uso por Inteligência Artificial, organizá-las em pastas, aplicar tags, definir diferentes níveis de privacidade e compartilhar suas obras em redes sociais. [cite_start]Além disso, o artista pode escolher se deseja visualizar métricas de engajamento, como número de curtidas, salvamentos e visualizações[cite: 48, 49].
* **Administrador do Sistema:** Responsável pela gestão geral da plataforma. [cite_start]Atua na manutenção técnica, moderação de conteúdo (incluindo análise de denúncias e violações das políticas de uso), administração de contas de usuários e configurações globais do sistema[cite: 50].
* **Visitante Público:** Usuário não autenticado que acessa o site sem possuir uma conta. [cite_start]Pode navegar pelos portfólios e visualizar apenas as obras marcadas como públicas, não tendo acesso a conteúdos protegidos ou restritos[cite: 51, 52].
* **Usuário Logado:** Usuário autenticado no sistema que não é necessariamente um artista. [cite_start]Pode interagir com as obras, realizando ações como curtir e salvar imagens, além de visualizar conteúdos privados disponibilizados pelos artistas que assim permitirem[cite: 53, 54].

### 2.2 Modelo de Casos de Uso e Histórias de Usuários


#### Casos de Uso


* [cite_start]**UC-01:** Publicar uma imagem criptografada anti-ia[cite: 58].
* [cite_start]**UC-02:** Compartilhar em outras redes sociais[cite: 59].
* [cite_start]**UC-03:** Curtir uma imagem[cite: 60].
* [cite_start]**UC-04:** Fazer login[cite: 61].

#### Histórias do Usuário


* [cite_start]**HS-01:** Como usuário gostaria de me cadastrar para que tenha acesso a novas funcionalidades[cite: 63].
* [cite_start]**HS-02:** Como artista gostaria de Adicionar tags às imagens para que facilite a pesquisa de minhas obras[cite: 64].
* [cite_start]**HS-03:** Como artista gostaria de me criar pasta de portfólio para facilitar a organização de minha obras[cite: 65].
* [cite_start]**HS-04:** Como artista gostaria de compartilhar em redes sociais para centralizar como poderia compartilhar minhas obras[cite: 66].
* [cite_start]**HS-05:** Como artista gostaria que minha obra ao ser publicada já esteja com proteção Anti-Ia para que não seja necessário utilizar outro software que faça isso[cite: 67].
* [cite_start]**HS-06:** Como artista gostaria de publicar imagens com senhas de privacidade para que consiga filtrar a visualização de certas obras através de apenas seguidores visualizarem ou apenas pessoas com senhas corretas[cite: 68].
* [cite_start]**HS-07:** Como visitante gostaria de visualizar imagens públicas para que o artista não seja prejudicado, apenas usuários com senha possam visualizá-la[cite: 69].
* [cite_start]**HS-08:** Como administrador gostaria de gerenciar usuários para poder excluir contas[cite: 70].
* [cite_start]**HS-09:** Como administrador gostaria de gerenciar denúncias para que seja possível verificar se a denúncia está correta ou não[cite: 72].
* [cite_start]**HS-10:** Como administrador gostaria de remover conteúdos que infringem regras da comunidade para que a comunidade esteja sempre dentro das regras[cite: 73].
* [cite_start]**HS-11:** Como usuário logado gostaria de favoritar uma imagem para salvá-la para que não precise procurar ela facilitando o acesso a obras que gostei[cite: 74].
* [cite_start]**HS-12:** Como usuário logado gostaria de seguir meu artistas preferidos para que facilite minha busca pelos artistas que gosto[cite: 75].
* [cite_start]**HS-13:** Como usuário logado dar likes em imagens para que o artista compreenda quando gosto de uma obra[cite: 76].

#### Diagrama de Casos de Uso

[cite_start]*(Aqui você cola a imagem do Diagrama de Casos de Uso)* [cite: 79-90]

### 2.3 Diagrama de Sequência do Sistema e Contrato de Operações


#### [cite_start]UC-01: Publicar uma imagem criptografada anti-ia [cite: 92]


[cite_start]**Contrato: Upload Imagem Com Proteção** [cite: 93]

| Campo | Descrição |
| :--- | :--- |
| **Operação** | [cite_start]`uploadImagem(titulo, descricao, arquivo, visibilidade)` [cite: 93] |
| **Referências** | [cite_start]Caso de uso: Publicar imagem com proteção anti-IA [cite: 93] |
| **Pré-condições** | [cite_start]Usuário deve estar autenticado.<br>Arquivo da imagem deve estar em formato permitido (ex: JPG, PNG)[cite: 93]. |
| **Pós-condições** | [cite_start]Imagem é armazenada.<br>Processo de proteção anti-IA é iniciado.<br>Imagem entra em estado de "EmVerificacao"[cite: 93]. |

[cite_start]*(Aqui você cola a imagem do Diagrama de Sequência UC-01)* [cite: 96-114]

---

#### [cite_start]UC-02: Compartilhar em outras redes sociais [cite: 115]


[cite_start]**Contrato: Compartilhar Imagem** [cite: 116, 121]

| Campo | Descrição |
| :--- | :--- |
| **Operação** | [cite_start]`CompartilharImagem(idImagem, plataforma)` [cite: 117, 122] |
| **Referências** | [cite_start]Caso de uso: Compartilhar imagem em redes sociais [cite: 118, 123] |
| **Pré-condições** | [cite_start]Usuário deve ser o proprietário da imagem.<br>Imagem deve estar publicada[cite: 119, 124, 125]. |
| **Pós-condições** | [cite_start]Imagem é compartilhada na plataforma externa (ex: Twitter).<br>Link é registrado no sistema para referência[cite: 120, 126, 127]. |

[cite_start]*(Aqui você cola a imagem do Diagrama de Sequência UC-02)* [cite: 128-141]

---

#### [cite_start]UC-03: Curtir uma imagem [cite: 143]


[cite_start]**Contrato: Curtir Imagem** [cite: 144]

| Campo | Descrição |
| :--- | :--- |
| **Operação** | [cite_start]`CurtirImagem(idImagem)` [cite: 144] |
| **Referências** | [cite_start]Caso de uso: Curtir imagem [cite: 144] |
| **Pré-condições** | [cite_start]Usuário deve estar autenticado.<br>Imagem deve estar publicada[cite: 144]. |
| **Pós-condições** | [cite_start]Registro de curtida é salvo.<br>Interface do usuário é atualizada para refletir o like[cite: 144]. |

[cite_start]*(Aqui você cola a imagem do Diagrama de Sequência UC-03)* [cite: 145-156]

---

## 3. Modelos de Projeto


### 3.1 Arquitetura


[cite_start]*(Aqui você cola a imagem do Diagrama de Arquitetura)* [cite: 162-224]

### 3.2 Diagrama de Componentes e Implantação


#### Componentes

[cite_start]*(Aqui você cola a imagem do Diagrama de Componentes)* [cite: 235-248]

#### Implantação

[cite_start]*(Aqui você cola a imagem do Diagrama de Implantação)* [cite: 249-264]

### 3.3 Diagrama de Classes


[cite_start]*(Aqui você cola a imagem do Diagrama de Classes)* [cite: 268-303]

### 3.4 Diagramas de Sequência


[cite_start]*(Aqui você cola a imagem do Diagrama de Sequência Geral)* [cite: 307-336]

### 3.5 Diagramas de Comunicação


[cite_start]*(Aqui você cola a imagem dos Diagramas de Comunicação)* [cite: 339-371]

### 3.6 Diagramas de Estados


[cite_start]*(Aqui você cola a imagem dos Diagramas de Estados)* [cite: 375-393]

## 4. Modelos de Dados


[cite_start]*(Aqui você cola a imagem do Modelo de Dados)* [cite: 396-446]

### Estratégia de Mapeamento dos Dados


* **Conversão de Classes para Tabelas:** Cada classe do sistema é transformada em uma tabela no banco de dados. [cite_start]Seus atributos (como textos, números e datas) tornam-se colunas, usando os tipos adequados do banco [cite: 448-450, 453].
* **Modelagem dos Relacionamentos:**
    * [cite_start]**Um-para-muitos (como Usuário → Imagens):** A tabela `Imagem` incluirá a coluna `idUsuario`, criando a ligação direta com o usuário dono da imagem[cite: 452, 454].
    * [cite_start]**Muitos-para-muitos (como Imagem ↔ Pastas):** Para representar esse tipo de relação, criamos uma tabela intermediária (`ImagemPasta`), que contém o ID da imagem e o ID da pasta, conectando ambas[cite: 455, 456].
* [cite_start]**Herança de Usuário:** Em vez de criar tabelas separadas para tipos de usuário, tudo será armazenado na tabela `Usuario`, diferenciando cada categoria por meio da coluna `tipo` (comum, artista, admin)[cite: 457, 458].
* [cite_start]**Ações Realizadas pelo Usuário:** Interações como curtidas e compartilhamentos serão registradas em tabelas próprias, que armazenam essas ações conforme acontecem no sistema [cite: 460-462].
* **Regras e Validações:** Condições para manter a integridade dos dados (como garantir que o e-mail não se repita) serão aplicadas tanto no banco como também na lógica da aplicação.
* **Outros Detalhes Importantes:**
    * [cite_start]Utilizaremos UUIDs como chaves primárias, assegurando que os identificadores sejam sempre únicos[cite: 468].
    * [cite_start]Colunas muito consultadas (como e-mail e IDs) receberão índices para melhorar o desempenho das buscas[cite: 469].
    * [cite_start]Os arquivos de imagem não serão armazenados diretamente no banco: salvaremos apenas o caminho/URL, enquanto o arquivo real ficará em algum serviço externo de armazenamento, como o AWS S3[cite: 470, 471].
