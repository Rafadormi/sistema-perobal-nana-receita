# Sistema SMS Perobal - Prescrições Médicas
Sistema de Prescrições Médicas da Secretaria Municipal de Saúde de Perobal/PR
# Sistema SMS Perobal - Prescrições Médicas

Este é um sistema completo para gerenciamento de prescrições médicas, desenvolvido para a Secretaria Municipal de Saúde de Perobal, Estado do Paraná. O sistema é composto por um backend em Flask (Python) e um frontend em React (TypeScript), ambos containerizados com Docker para facilitar a implantação e o gerenciamento.

## Funcionalidades Principais

- **Autenticação e Autorização**: Sistema de login seguro com controle de acesso baseado em perfis (Administrador, SMS Perobal, Médico, Equipe, Setor MAC).
- **Gestão de Pacientes**: Cadastro, consulta, edição e exclusão de informações de pacientes, incluindo dados demográficos e de contato.
- **Gestão de Médicos**: Cadastro e gerenciamento de médicos, com informações de CRM e especialidade.
- **Gestão de Medicamentos**: Cadastro e controle de medicamentos, incluindo informações de concentração, forma e categoria (comum, controlado).
- **Sistema de Prescrições**: Criação de novas prescrições, associação a pacientes e médicos, e registro dos medicamentos prescritos.
- **Geração de PDF**: Geração automática de receitas médicas em formato PDF, prontas para impressão.
- **Relatórios e Auditoria**: Dashboards e logs para monitoramento de atividades e geração de relatórios.
- **Configurações do Sistema**: Gerenciamento de informações da instituição e outras configurações gerais.

## Tecnologias Utilizadas

### Backend
- **Linguagem**: Python 3.11
- **Framework**: Flask
- **ORM**: SQLAlchemy
- **Banco de Dados**: PostgreSQL
- **Autenticação**: Flask-JWT-Extended
- **Geração de PDF**: WeasyPrint
- **Containerização**: Docker

### Frontend
- **Framework**: React (com TypeScript)
- **Estilização**: Tailwind CSS
- **Gerenciamento de Estado**: React Context API
- **Requisições HTTP**: Axios
- **Validação de Formulários**: Formik e Yup
- **Roteamento**: React Router DOM
- **Containerização**: Docker

## Como Rodar o Projeto Localmente (Docker Desktop)

Para rodar este projeto em seu ambiente local, você precisará ter o Docker Desktop instalado e configurado. Siga os passos abaixo:

### Pré-requisitos

- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [Git](https://git-scm.com/)

### 1. Clonar o Repositório

Abra seu terminal ou prompt de comando e execute o seguinte comando para clonar o repositório:

```bash
git clone [URL_DO_SEU_REPOSITORIO]
cd sms-perobal
```

**Nota**: Substitua `[URL_DO_SEU_REPOSITORIO]` pelo URL real do repositório onde este projeto será hospedado.

### 2. Configurar Variáveis de Ambiente

Navegue até o diretório `sms-perobal` e crie um arquivo `.env` na raiz do projeto, baseado no `.env.example` que será fornecido no diretório `backend`.

```bash
cp backend/.env.example .env
```

Edite o arquivo `.env` e preencha as variáveis de ambiente com valores seguros. Por exemplo:

```
# .env
SECRET_KEY=sua_chave_secreta_aqui
JWT_SECRET_KEY=sua_chave_jwt_secreta_aqui
POSTGRES_PASSWORD=sua_senha_postgres_aqui
GRAFANA_ADMIN_USER=admin
GRAFANA_ADMIN_PASSWORD=sua_senha_grafana_aqui
```

### 3. Iniciar o Sistema com Docker Compose

No diretório `sms-perobal`, execute o seguinte comando para construir as imagens Docker e iniciar todos os serviços:

```bash
docker compose up --build -d
```

- `--build`: Garante que as imagens Docker sejam construídas a partir dos Dockerfiles.
- `-d`: Inicia os serviços em modo detached (em segundo plano).

### 4. Acessar o Sistema

Após os serviços serem iniciados (pode levar alguns minutos na primeira vez), você poderá acessar o sistema:

- **Frontend**: Abra seu navegador e acesse `http://localhost`
- **Backend API (Swagger UI)**: `http://localhost/api/docs`

### 5. Parar o Sistema

Para parar todos os serviços e remover os containers, execute:

```bash
docker compose down
```

Para parar e remover também os volumes (dados do banco de dados), use:

```bash
docker compose down -v
```

## Estrutura do Projeto

```
sms-perobal/
├── backend/                # Código-fonte do backend (Flask, Python)
├── frontend/               # Código-fonte do frontend (React, TypeScript)
├── docker-compose.yml      # Configuração do Docker Compose para desenvolvimento
├── .env.example            # Exemplo de variáveis de ambiente
├── .env                    # Variáveis de ambiente (não versionado)
└── README.md               # Este arquivo
```

## Contribuição

Instruções sobre como contribuir para o projeto serão adicionadas aqui.

## Licença

Informações sobre a licença do projeto serão adicionadas aqui.
