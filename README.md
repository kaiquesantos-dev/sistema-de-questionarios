# Sistema de Questionários

Aplicação web para criação e gerenciamento de questionários: é possível cadastrar perguntas, agrupá-las em formulários, coletar respostas de participantes e consultar os resultados recebidos.

## Funcionalidades

- **Perguntas**: cadastro de perguntas de diferentes tipos (múltipla escolha, checkbox, texto curto, texto longo), com suporte a perguntas obrigatórias.
- **Formulários**: montagem de formulários a partir do banco de perguntas, com controle de status (rascunho/publicado/encerrado) e período de vigência.
- **Respostas**: preenchimento de formulários publicados e consulta das respostas recebidas por formulário.
- **Regras de integridade**: um formulário que já recebeu respostas não pode ter suas perguntas alteradas nem ser excluído (apenas encerrado), para preservar o histórico de respostas.

## Tecnologias

- **HTML, CSS e JavaScript puro** (sem frameworks) no front-end.
- **[json-server](https://github.com/typicode/json-server)** simulando uma API REST a partir do arquivo `db.json`, usada como backend fake para as operações de CRUD.
- **[SweetAlert2](https://sweetalert2.github.io/)** para confirmações e mensagens de feedback ao usuário.
- **[Vanta.js](https://www.vantajs.com/) + Three.js** para a animação de fundo na página inicial.
- Fonte **Poppins** via Google Fonts.

## Como executar

1. Instale as dependências:
   ```bash
   npm install
   ```
2. Suba a API fake (json-server, na porta 3000, observando `db.json`):
   ```bash
   npm run server
   ```
3. Abra o arquivo `pages/index.html` no navegador (ou sirva a pasta com uma extensão como o Live Server) para acessar a aplicação. As páginas de perguntas, formulários e respostas consomem a API em `http://localhost:3000`.

## Estrutura do projeto

```
pages/        páginas HTML (index, perguntas, formularios, responder, respostas)
js/           lógica de cada página + api.js com as funções de acesso à API
css/          estilos da aplicação
db.json       "banco de dados" usado pelo json-server
```

## Contexto

Projeto desenvolvido como exercício de fixação sobre consumo de API REST (fetch, CRUD) e manipulação de DOM em JavaScript puro, com regras de negócio adicionais para simular um cenário mais próximo de um sistema real de coleta de dados.
