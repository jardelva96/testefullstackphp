# Desafio Fullstack PHP

## Sobre o Projeto

Este projeto é um desafio de desenvolvimento fullstack, onde o objetivo é criar uma aplicação de gerenciamento de tarefas (To-Do List) com as seguintes tecnologias:

- **Backend**: Laravel (PHP)
- **Frontend**: Vue.js
- **Banco de Dados**: SQLite (para persistência de dados)
- **Orquestração**: Docker (para ambientes isolados e configuráveis)
- **Monitoramento**: Prometheus e Grafana para monitoramento de métricas

### Objetivos

- **Backend**: Criar uma API RESTful para gerenciamento de tarefas com funcionalidades de CRUD (Create, Read, Update, Delete) e autenticação de usuários.
- **Frontend**: Desenvolver uma interface para o usuário, permitindo que ele interaja com as tarefas, criando, editando e removendo-as.
- **Rotina Diária**: No backend, será implementada uma rotina diária que coleta notícias da UOL e envia para todos os usuários cadastrados. Nenhum usuário pode receber a mesma notícia duplicada.

## Tecnologias Usadas

- **PHP (Laravel)** para o backend
- **Vue.js** para o frontend
- **SQLite** para o banco de dados
- **Docker** para orquestrar o ambiente de desenvolvimento e produção
- **Prometheus e Grafana** para monitoramento
- **Git** e **GitHub/Bitbucket** para controle de versão e colaboração

## Requisitos

Antes de rodar o projeto, certifique-se de ter os seguintes requisitos instalados:

- Docker (para criar contêineres)
- Composer (para gerenciar dependências PHP)
- Node.js e npm (para rodar o frontend Vue.js)
- Git (para controle de versão)

## Instalação

**Clonando o repositório**

   Clone o repositório com o seguinte comando:

   ```bash
   git clone https://github.com/jardelva96/testefullstackphp.git
   ```
- Configuração do Backend (Laravel)

- Após clonar o repositório, entre na pasta do backend e instale as dependências:

```bash
cd desafiofullstackback
composer install
```
- Copie o arquivo .env.example para .env:
```bash
cp .env.example .env
```
- Gere a chave do aplicativo:
```bash
php artisan key:generate
```
- Certifique-se de que a configuração do banco de dados (DB_CONNECTION=sqlite) está correta no arquivo .env.
- Configuração do Frontend (Vue.js)

### Entre na pasta do frontend e instale as dependências:
```bash
cd desafiovuejs
npm install
```
- Inicie o servidor de desenvolvimento:
 ```bash
npm run serve
```
Executando com Docker

### Se você quiser rodar a aplicação no Docker, basta usar o comando abaixo:
```bash
docker-compose up --build
```
- Isso irá subir os contêineres para o frontend, backend e outros serviços necessários.

## Funcionalidades
### Backend:
API RESTful com autenticação de usuários.
CRUD para gerenciamento de tarefas.
Rotina diária para coletar notícias da UOL e enviar para os usuários cadastrados.
Frontend:
- Possibilidade de adicionar, editar e excluir tarefas.
- Monitoramento
- O sistema usa Prometheus e Grafana para coletar métricas e monitorar a saúde do sistema.
- Passos para visualizar as métricas:
- Acesse o Prometheus na URL http://localhost:9090.
- Acesse o Grafana na URL http://localhost:3001.
- Como Funciona a Coleta de Notícias
- A coleta das notícias é feita de forma automática através de uma rotina que é executada diariamente. O processo é o seguinte:

O comando php artisan fetch:uol-news coleta as notícias do feed RSS da UOL (https://rss.uol.com.br/feed/tecnologia.xml).
As notícias são então salvas no banco de dados e enviadas para os usuários cadastrados via e-mail. Nenhum usuário recebe a mesma notícia duas vezes.
