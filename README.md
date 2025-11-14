# Documentação de Projeto: ShieldFolio


**Versão:** 1.2
**Autora:** Giovanna Lima Torres Guasch
**Data:** 11/11/2025
*Projeto de sistema elaborado como parte da disciplina Projeto de Software.*

## 1. Introdução


Este documento reúne duas etapas principais: (1) a criação e revisão dos modelos de domínio e (2) o desenvolvimento dos modelos de projeto do sistema ShieldFolio.

Artistas digitais enfrentam hoje grandes dificuldades ao divulgar seus trabalhos na internet, principalmente no que diz respeito à proteção contra o uso indevido por ferramentas de Inteligência Artificial. A maioria das plataformas de portfólio não dispõe de recursos eficientes de segurança ou controle de privacidade, o que torna as imagens suscetíveis a cópias, reutilizações ou extrações por modelos de IA generativa.

O ShieldFolio propõe-se a ser uma plataforma web voltada à exibição e ao gerenciamento de portfólios artísticos, priorizando a proteção das imagens e a organização personalizada.

## 2. Modelos de Usuário e Requisitos

### 2.1 Descrição de Atores


* **Artista:** É o principal usuário do sistema. Pode criar uma conta, enviar imagens com proteção contra uso por Inteligência Artificial, organizá-las em pastas, aplicar tags, definir diferentes níveis de privacidade e compartilhar suas obras em redes sociais. Além disso, o artista pode escolher se deseja visualizar métricas de engajamento, como número de curtidas, salvamentos e visualizações.
* **Administrador do Sistema:** Responsável pela gestão geral da plataforma. Atua na manutenção técnica, moderação de conteúdo (incluindo análise de denúncias e violações das políticas de uso), administração de contas de usuários e configurações globais do sistema.
* **Visitante Público:** Usuário não autenticado que acessa o site sem possuir uma conta. Pode navegar pelos portfólios e visualizar apenas as obras marcadas como públicas, não tendo acesso a conteúdos protegidos ou restritos.
* **Usuário Logado:** Usuário autenticado no sistema que não é necessariamente um artista. Pode interagir com as obras, realizando ações como curtir e salvar imagens, além de visualizar conteúdos privados disponibilizados pelos artistas que assim permitirem.

### 2.2 Modelo de Casos de Uso e Histórias de Usuários


#### Casos de Uso


* **UC-01:** Publicar uma imagem criptografada anti-ia.
* **UC-02:** Compartilhar em outras redes sociais.
* **UC-03:** Curtir uma imagem.
* **UC-04:** Fazer login.

#### Histórias do Usuário


* **HS-01:** Como usuário gostaria de me cadastrar para que tenha acesso a novas funcionalidades.
* **HS-02:** Como artista gostaria de Adicionar tags às imagens para que facilite a pesquisa de minhas obras.
* **HS-03:** Como artista gostaria de me criar pasta de portfólio para facilitar a organização de minha obras.
* **HS-04:** Como artista gostaria de compartilhar em redes sociais para centralizar como poderia compartilhar minhas obras.
* **HS-05:** Como artista gostaria que minha obra ao ser publicada já esteja com proteção Anti-Ia para que não seja necessário utilizar outro software que faça isso.
* **HS-06:** Como artista gostaria de publicar imagens com senhas de privacidade para que consiga filtrar a visualização de certas obras através de apenas seguidores visualizarem ou apenas pessoas com senhas corretas.
* **HS-07:** Como visitante gostaria de visualizar imagens públicas para que o artista não seja prejudicado, apenas usuários com senha possam visualizá-la.
* **HS-08:** Como administrador gostaria de gerenciar usuários para poder excluir contas.
* **HS-09:** Como administrador gostaria de gerenciar denúncias para que seja possível verificar se a denúncia está correta ou não.
* **HS-10:** Como administrador gostaria de remover conteúdos que infringem regras da comunidade para que a comunidade esteja sempre dentro das regras.
* **HS-11:** Como usuário logado gostaria de favoritar uma imagem para salvá-la para que não precise procurar ela facilitando o acesso a obras que gostei.
* **HS-12:** Como usuário logado gostaria de seguir meu artistas preferidos para que facilite minha busca pelos artistas que gosto.
* **HS-13:** Como usuário logado dar likes em imagens para que o artista compreenda quando gosto de uma obra.

#### Diagrama de Casos de Uso

<img src="https://github.com/GioGuasch/Trabalho-2---Documenta-o-de-Projeto-de-Software/blob/main/Imagens/Casos%20de%20uso.png">

### 2.3 Diagrama de Sequência do Sistema e Contrato de Operações


#### UC-01: Publicar uma imagem criptografada anti-ia


**Contrato: Upload Imagem Com Proteção**

| Campo | Descrição |
| :--- | :--- |
| **Operação** | `uploadImagem(titulo, descricao, arquivo, visibilidade)` |
| **Referências** | Caso de uso: Publicar imagem com proteção anti-IA |
| **Pré-condições** | Usuário deve estar autenticado.<br>Arquivo da imagem deve estar em formato permitido (ex: JPG, PNG). |
| **Pós-condições** | Imagem é armazenada.<br>Processo de proteção anti-IA é iniciado.<br>Imagem entra em estado de "EmVerificacao". |

<img src="https://github.com/GioGuasch/Trabalho-2---Documenta-o-de-Projeto-de-Software/blob/main/Imagens/UC01.png">

---

#### UC-02: Compartilhar em outras redes sociais


**Contrato: Compartilhar Imagem**

| Campo | Descrição |
| :--- | :--- |
| **Operação** | `CompartilharImagem(idImagem, plataforma)` |
| **Referências** | Caso de uso: Compartilhar imagem em redes sociais |
| **Pré-condições** | Usuário deve ser o proprietário da imagem.<br>Imagem deve estar publicada. |
| **Pós-condições** | Imagem é compartilhada na plataforma externa (ex: Twitter).<br>Link é registrado no sistema para referência. |

<img src="https://github.com/GioGuasch/Trabalho-2---Documenta-o-de-Projeto-de-Software/blob/main/Imagens/UC02.png">

---

#### UC-03: Curtir uma imagem


**Contrato: Curtir Imagem**

| Campo | Descrição |
| :--- | :--- |
| **Operação** | `CurtirImagem(idImagem)` |
| **Referências** | Caso de uso: Curtir imagem |
| **Pré-condições** | Usuário deve estar autenticado.<br>Imagem deve estar publicada. |
| **Pós-condições** | Registro de curtida é salvo.<br>Interface do usuário é atualizada para refletir o like. |

<img src="https://github.com/GioGuasch/Trabalho-2---Documenta-o-de-Projeto-de-Software/blob/main/Imagens/UC03.png">

---

## 3. Modelos de Projeto


### 3.1 Arquitetura


<img src="https://github.com/GioGuasch/Trabalho-2---Documenta-o-de-Projeto-de-Software/blob/main/Imagens/Arquitetura.png">

### 3.2 Diagrama de Componentes e Implantação


#### Componentes

<img src="https://github.com/GioGuasch/Trabalho-2---Documenta-o-de-Projeto-de-Software/blob/main/Imagens/Componentes.png">

#### Implantação

<img src="https://github.com/GioGuasch/Trabalho-2---Documenta-o-de-Projeto-de-Software/blob/main/Imagens/Implantação.png">

### 3.3 Diagrama de Classes

<img src="https://github.com/GioGuasch/Trabalho-2---Documenta-o-de-Projeto-de-Software/blob/main/Imagens/DiagramaDeClasses.png">

### 3.4 Diagramas de Sequência

<img src="https://github.com/GioGuasch/Trabalho-2---Documenta-o-de-Projeto-de-Software/blob/main/Imagens/Sequencia.png">

### 3.5 Diagramas de Comunicação

<img src="https://github.com/GioGuasch/Trabalho-2---Documenta-o-de-Projeto-de-Software/blob/main/Imagens/Diagrama%20de%20Comunicacao.png">

### 3.6 Diagramas de Estados

<img src="https://github.com/GioGuasch/Trabalho-2---Documenta-o-de-Projeto-de-Software/blob/main/Imagens/Estados.png">

## 4. Modelos de Dados

<img src="https://github.com/GioGuasch/Trabalho-2---Documenta-o-de-Projeto-de-Software/blob/main/Imagens/ModelodeDados.png">

### Estratégia de Mapeamento dos Dados


* **Conversão de Classes para Tabelas:** Cada classe do sistema é transformada em uma tabela no banco de dados. Seus atributos (como textos, números e datas) tornam-se colunas, usando os tipos adequados do banco.
* **Modelagem dos Relacionamentos:**
    * **Um-para-muitos (como Usuário → Imagens):** A tabela `Imagem` incluirá a coluna `idUsuario`, criando a ligação direta com o usuário dono da imagem.
    * **Muitos-para-muitos (como Imagem ↔ Pastas):** Para representar esse tipo de relação, criamos uma tabela intermediária (`ImagemPasta`), que contém o ID da imagem e o ID da pasta, conectando ambas.
* **Herança de Usuário:** Em vez de criar tabelas separadas para tipos de usuário, tudo será armazenado na tabela `Usuario`, diferenciando cada categoria por meio da coluna `tipo` (comum, artista, admin).
* **Ações Realizadas pelo Usuário:** Interações como curtidas e compartilhamentos serão registradas em tabelas próprias, que armazenam essas ações conforme acontecem no sistema.
* **Regras e Validações:** Condições para manter a integridade dos dados (como garantir que o e-mail não se repita) serão aplicadas tanto no banco como também na lógica da aplicação.
* **Outros Detalhes Importantes:**
    * Utilizaremos UUIDs como chaves primárias, assegurando que os identificadores sejam sempre únicos.
    * Colunas muito consultadas (como e-mail e IDs) receberão índices para melhorar o desempenho das buscas.
    * Os arquivos de imagem não serão armazenados diretamente no banco: salvaremos apenas o caminho/URL, enquanto o arquivo real ficará em algum serviço externo de armazenamento, como o AWS S3.
