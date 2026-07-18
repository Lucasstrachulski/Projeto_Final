# 🦁 Projeto Final LionsDev | Aplicação Full-Stack

<p align="center">
  <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" alt="Node.js"/>
  <img src="https://img.shields.io/badge/Express-000000?style=for-the-badge&logo=express&logoColor=white" alt="Express"/>
  <img src="https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB"/>
  <img src="https://img.shields.io/badge/JWT-000000?style=for-the-badge&logo=jsonwebtokens&logoColor=white" alt="JWT"/>
  <img src="https://img.shields.io/badge/Render-00E676?style=for-the-badge&logo=render&logoColor=white" alt="Render"/>
</p>

---

## 📝 Visão Geral
Esta aplicação full-stack representa o **Projeto Final de Graduação** do programa de engenharia de software **LionsDev** (Turma: Lions Dev). Construído sobre uma base arquitetural sólida, o ecossistema entrega autenticação segura, persistência de dados nativa em nuvem, camadas de domínio desacopladas e uma integração completa de ponta a ponta com a interface frontend.

---

## 🛠️ Tecnologias e Dependências
O ecossistema do projeto foi construído utilizando as seguintes ferramentas obrigatórias:

* **Ambiente de Execução:** Node.js (Versão LTS)
* **Framework Web:** Express.js
* **Mapeamento de Dados (ODM):** Mongoose / MongoDB Atlas
* **Segurança e Criptografia:** `bcryptjs` (Hash de senhas) e `jsonwebtoken` (Autenticação Bearer Token)
* **Gerenciamento de Ambiente:** `dotenv`
* **Ferramenta de Testes:** Postman (Coleção de testes inclusa no repositório)
* **Ambiente de Hospedagem:** Render Web Services

---

## ✨ Funcionalidades Principais
* **Sistema de Autenticação Robusto:** Cadastro de usuários com senhas protegidas por hash e fluxo de login com emissão de tokens JWT.
* **Controle de Acesso Protegido:** Rotas privadas do ecossistema bloqueadas por middlewares de validação de token.
* **Operações CRUD Completas:** Gerenciamento e manipulação total de dados para pelo menos 2 entidades do domínio.
* **Persistência na Nuvem:** Todas as operações realizam modificações em tempo real diretamente no MongoDB Atlas.
* **Regra de Negócio entre Entidades:** Lógica de fluxo exclusiva que conecta e valida interações cruzadas entre diferentes coleções de dados.

---

## 🗂️ Arquitetura do Sistema e Camadas
O núcleo do sistema foi construído diretamente sobre o **Boilerplate oficial da LionsDev**, implementando um modelo de arquitetura estritamente desacoplado para garantir a separação de responsabilidades:

```text
src/
├── 📄 app.js             # Interceptadores globais, orquestração de rotas e tratamento de 404
├── 📄 server.js          # Inicialização do core, carregamento do ambiente e driver do MongoDB
├── 📂 config/            # Drivers de infraestrutura (conexões database.js)
├── 📂 controllers/       # Ingestão de requisições HTTP e entrega de respostas JSON estruturadas
├── 📂 middlewares/       # Barreiras de segurança, proteção de rotas e pipelines de validação
├── 📂 models/            # Schemas rígidos do Mongoose ODM para as coleções
├── 📂 repositories/      # Data Access Objects (DAO) que comunicam diretamente com o banco de dados
├── 📂 routes/            # Roteamento de rede e definições das cadeias de middlewares
├── 📂 services/          # Domínio puro de negócios isolado e restrições de validação lógica
└── 📂 utils/             # Motores utilitários reutilizáveis (geração dinâmica de erros customizados)
