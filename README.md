# Hub — Qualidade EAD Unicive

Portal dinâmico e responsivo desenvolvido para centralizar os links e ferramentas essenciais da equipe de Qualidade EAD. O projeto apresenta uma arquitetura *serverless*, permitindo atualizações em tempo real através de um painel de controle integrado e armazenamento via JSONBin.

##  Funcionalidades

* **Interface Otimizada:** Visualização em grid responsiva com cartões de links interativos, organizados por *badges* de identificação visual (Formulários, Planilhas, Documentos).
* **Modo Claro/Escuro (Dark Mode):** Alternância de tema nativa com persistência de dados no navegador (`localStorage`).
* **Painel de Administração (`/admin.html`):** Área restrita protegida por senha para o gerenciamento total da página (títulos, subtítulos, cores de destaque e lista de links) sem a necessidade de editar o código-fonte.
* **Sincronização em Nuvem (JSONBin):** Leitura e escrita de dados de forma assíncrona utilizando a API do JSONBin.io, eliminando a exigência de um *backend* ou banco de dados tradicional.

##  Stack Tecnológico

* **Front-end:** HTML5, CSS3, Vanilla JavaScript.
* **Armazenamento de Dados:** JSONBin.io (API REST).
* **Design:** CSS customizado com variáveis globais (Tokens) e ícones SVG inline.

##  Instruções de Uso e Configuração

### 1. Acesso Padrão
Para visualizar o portal localmente, basta executar o arquivo `index.html` em qualquer navegador web atualizado. Os dados iniciais serão carregados a partir do arquivo estático `data.js` ou da nuvem, caso configurado.

### 2. Acessando o Painel de Controle
* Navegue até a página `admin.html`.
* Insira a credencial de acesso. A senha padrão nativa do sistema é: `unicv`.
* Neste ambiente, é possível reordenar, criar, editar ou excluir links, além de personalizar a identidade visual da página.

### 3. Configurando a Nuvem (Primeiro Setup)
Para que as edições feitas no painel reflitam na versão pública para todos os usuários:
1.  No painel de administração, acesse a aba **Integração JSONBin**.
2.  Insira uma *Master Key* válida gerada na plataforma [JSONBin.io](https://jsonbin.io/).
3.  Clique em **Salvar na Nuvem**. O sistema irá criar automaticamente um novo banco de dados (Bin ID).
4.  Após o sucesso da operação, clique no botão **Baixar data.js** e substitua o arquivo original na raiz do projeto. Este passo é necessário apenas uma vez para fixar o `JSONBIN_ID` definitivo no código.

##  Estrutura de Diretórios e Arquivos

* `index.html`: Interface principal e pública (Hub de links).
* `admin.html`: Painel de controle e gerenciamento.
* `data.js`: Arquivo que armazena a estrutura de dados de *fallback* e a variável global do ID do JSONBin.
* `logo.png` / `favicon.png`: Ativos visuais e de marca (Unicive).
* `.gitattributes`: Regras de normalização de texto e quebras de linha para o controle de versão.
