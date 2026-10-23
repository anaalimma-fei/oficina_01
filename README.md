# 🚗 AutoMecânica Pro — Sistema Integrado de Gestão de Oficina

## 📌 Sobre o Projeto

O **AutoMecânica Pro** é um sistema web desenvolvido para facilitar a gestão de uma oficina mecânica, permitindo organizar clientes, veículos e agendamentos de serviços em um único ambiente.

O projeto foi desenvolvido com foco na automatização dos processos da oficina, na organização das informações, na segurança dos dados e na facilidade de utilização.

Esta aplicação faz parte de uma atividade técnica do **SAEP / SENAI**, envolvendo conceitos de desenvolvimento web, banco de dados, segurança da informação e organização de sistemas.

## 🎯 Objetivo

Desenvolver um sistema que melhore o controle operacional de uma oficina mecânica, reduzindo erros nos cadastros, evitando conflitos de horários e facilitando o acesso às informações de clientes, veículos e serviços agendados.

## ⚙️ Funcionalidades

- 🔐 **Login e autenticação:** acesso ao sistema por meio de usuário e senha.
- ⏱️ **Controle de sessão:** encerramento da sessão após 15 minutos de inatividade.
- 📊 **Dashboard:** painel principal com identificação do usuário e acesso às funcionalidades.
- 👥 **Cadastro de clientes:** registro de nome, CPF, telefone, e-mail e endereço.
- 🔎 **Busca de clientes:** pesquisa de clientes cadastrados.
- ✏️ **Edição de clientes:** atualização das informações cadastrais.
- 🚘 **Cadastro de veículos:** registro de placa, marca, modelo, ano, cor e quilometragem, associado a um cliente.
- 📅 **Agendamento de serviços:** organização dos atendimentos por data e horário.
- 🔄 **Reagendamento:** alteração da data e do horário de serviços já cadastrados.
- 📋 **Listagem de agendamentos:** exibição das informações relacionadas aos clientes, veículos e serviços.
- 🛡️ **Segurança de dados:** utilização de hash de senhas e proteção dos dados pessoais.

## 🛠️ Tecnologias Utilizadas

| Tecnologia | Utilização |
|---|---|
| Python 3.10+ | Desenvolvimento do backend |
| Flask 3.0 | Framework para aplicação web |
| MySQL 8.0 | Banco de dados relacional |
| HTML5 | Estrutura das páginas |
| CSS3 | Estilização e layout |
| JavaScript | Interatividade e validações |
| Bcrypt | Hash de senhas e proteção de dados |
| InnoDB | Integridade e transações do banco de dados |

## 🗄️ Banco de Dados

O sistema utiliza o MySQL para armazenar e organizar as informações em quatro tabelas principais:

- **usuarios:** dados dos usuários que acessam o sistema.
- **clientes:** informações cadastrais dos clientes.
- **veiculos:** dados dos veículos associados aos clientes.
- **agendamentos:** informações sobre os serviços, datas, horários, status e valores estimados.

O banco utiliza relacionamentos por chaves estrangeiras (*Foreign Keys*) para manter a integridade dos dados.

## 🔒 Segurança da Informação

O projeto considera práticas importantes de segurança, incluindo:

- Armazenamento de senhas utilizando hash Bcrypt.
- Proteção de dados pessoais conforme os princípios da LGPD.
- Validação de CPF com 11 dígitos numéricos.
- Controle de sessão com tempo de expiração.
- Restrição de acesso a usuários autenticados.
- Integridade referencial no banco de dados.

**Observação técnica:** o Bcrypt é indicado para hash de senhas e não para criptografia reversível de CPF. Como o sistema precisa consultar e exibir o CPF, sua proteção deve utilizar criptografia adequada quando for necessário recuperar o valor original, podendo ser combinada com um hash para pesquisas. A implementação deve seguir os requisitos aplicáveis da LGPD.

## 📋 Regras de Negócio

- O usuário deve estar autenticado para acessar as funcionalidades protegidas.
- Credenciais incorretas devem impedir o acesso ao sistema.
- O CPF deve conter exatamente 11 dígitos numéricos.
- Todo veículo deve estar associado a um cliente existente.
- Os agendamentos devem ser apresentados em ordem cronológica.
- O reagendamento deve permitir alterar somente a data e o horário.
- O sistema deve manter a consistência dos relacionamentos entre clientes, veículos e agendamentos.

## 🚀 Como Executar o Projeto

### Pré-requisitos

- Python 3.10 ou superior.
- MySQL 8.0.
- Git.
- Um editor de código, como o Visual Studio Code.

### 1. Clonar o repositório

```bash
git clone URL_DO_SEU_REPOSITORIO
```

Entre na pasta do projeto:

```bash
cd AutoMecanica-Pro
```

### 2. Criar um ambiente virtual

```bash
python -m venv venv
```

Ative o ambiente virtual.

**Windows:**

```bash
venv\Scripts\activate
```

### 3. Instalar as dependências

```bash
pip install Flask bcrypt mysql-connector-python
```

### 4. Configurar o banco de dados

Abra o MySQL e execute o script `saep_db.sql` para criar o banco de dados e suas tabelas.

Verifique se as configurações de conexão correspondem ao ambiente local. Utilize variáveis de ambiente para armazenar credenciais e não publique senhas reais no repositório.

### 5. Executar a aplicação

Se o arquivo principal for `app.py`, execute:

```bash
python app.py
```

Depois, acesse o endereço local informado pelo Flask no terminal, normalmente:

```text
http://127.0.0.1:5000
```

*Os comandos podem precisar de ajustes conforme a estrutura final do projeto.*

## 📁 Estrutura do Projeto

Uma possível organização dos arquivos é:

```text
AutoMecanica-Pro/
│
├── app.py
├── autenticacao.py
├── clientes.py
├── veiculos.py
├── agendamento.py
├── rotas.py
├── saep_db.sql
│
├── templates/
│   ├── login.html
│   ├── dashboard.html
│   ├── clientes.html
│   ├── veiculos.html
│   └── agendamentos.html
│
├── static/
│   ├── css/
│   │   └── style.css
│   └── js/
│       └── script.js
│
├── requirements.txt
├── .gitignore
└── README.md
```

*Essa estrutura é uma sugestão baseada nos requisitos da documentação e deve ser ajustada aos arquivos realmente existentes no projeto.*

## 🎓 Aprendizados

O desenvolvimento deste projeto permite aplicar conhecimentos de:

- Programação backend com Python e Flask.
- Desenvolvimento de interfaces com HTML, CSS e JavaScript.
- Modelagem e manipulação de bancos de dados MySQL.
- Operações CRUD: cadastro, consulta, atualização e exclusão.
- Relacionamentos entre tabelas.
- Autenticação e segurança de aplicações web.
- Validação de dados e regras de negócio.
- Proteção de dados pessoais e conceitos da LGPD.

## 👩‍💻 Contexto Acadêmico

**Projeto:** AutoMecânica Pro — Sistema Integrado de Gestão de Oficina  
**Atividade:** SAEP — Desenvolvimento de Sistemas  
**Instituição:** Escola SENAI A. Jacob Lafer  
**Curso:** Técnico em Desenvolvimento de Sistemas  
**Versão:** 1.0.0 — Release SAEP  
**Data:** Outubro de 2026

## 📄 Licença

Projeto desenvolvido para fins educacionais no contexto da atividade SAEP / SENAI.
