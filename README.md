# ⚙️ Sistema de Gerenciamento para Oficina Mecânica — SAEP/SENAI

**Projeto acadêmico de Desenvolvimento de Sistemas**

![Python](https://img.shields.io/badge/Python-3.13-blue?logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-3.0.3-black?logo=flask)
![MySQL](https://img.shields.io/badge/MySQL-Database-4479A1?logo=mysql&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML5-Frontend-E34F26?logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-Styles-1572B6?logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-Frontend-F7DF1E?logo=javascript&logoColor=black)

## 📌 Sobre o projeto

O **Sistema de Gerenciamento para Oficina Mecânica** é um projeto acadêmico desenvolvido com base no guia de implementação do SAEP/SENAI. Seu objetivo é organizar e facilitar o gerenciamento das principais atividades de uma oficina mecânica por meio de uma aplicação web conectada a um banco de dados relacional.

O sistema foi planejado para centralizar informações de funcionários, clientes, veículos e agendamentos de serviços, oferecendo uma estrutura organizada para cadastro, consulta, edição e exclusão de registros.

O projeto utiliza Python com Flask no backend, MySQL para armazenamento dos dados e HTML, CSS e JavaScript para a interface.

## 🎯 Objetivos

- Desenvolver uma aplicação web para gerenciamento de uma oficina mecânica.
- Implementar conexão entre Python e MySQL.
- Organizar clientes e seus respectivos veículos.
- Permitir o controle de agendamentos de serviços.
- Implementar autenticação de usuários.
- Aplicar validações de dados e consultas ao banco.
- Organizar o código em módulos independentes.
- Desenvolver uma interface web para interação com o sistema.
- Praticar os conhecimentos adquiridos no curso de Desenvolvimento de Sistemas.

## 🛠️ Tecnologias utilizadas

| Tecnologia | Finalidade |
|---|---|
| Python | Linguagem principal do backend |
| Flask | Criação da aplicação web e gerenciamento das rotas |
| MySQL | Banco de dados relacional |
| mysql-connector-python | Conexão do Python com o MySQL |
| Bcrypt | Geração e verificação de hashes |
| Werkzeug | Ferramentas utilizadas pelo Flask |
| HTML5 | Estrutura das páginas |
| CSS3 | Estilização da interface |
| JavaScript | Interações no frontend |
| Git e GitHub | Versionamento e compartilhamento do código |

## ⚙️ Funcionalidades previstas

### 🔐 Autenticação de usuários
- Tela de login.
- Verificação das credenciais no banco de dados.
- Controle de sessão.
- Identificação do usuário autenticado.
- Exibição do nome e cargo do usuário.
- Encerramento seguro da sessão.
- Configuração de expiração de sessão de 15 minutos.

### 👥 Gerenciamento de clientes
- Cadastro de clientes.
- Listagem dos clientes registrados.
- Pesquisa por nome, CPF, e-mail ou telefone.
- Edição dos dados cadastrados.
- Exclusão de registros.
- Validação para verificar se o CPF contém 11 dígitos.
- Armazenamento de hash do CPF conforme previsto no guia.

### 🚗 Gerenciamento de veículos
- Cadastro de veículos.
- Associação obrigatória entre veículo e cliente.
- Consulta dos veículos cadastrados.
- Edição das informações.
- Exclusão de registros.
- Armazenamento de placa, marca, modelo, ano, cor e quilometragem.

### 📅 Gerenciamento de agendamentos
- Cadastro de serviços agendados.
- Associação entre cliente e veículo.
- Registro de data e horário.
- Descrição do serviço solicitado.
- Registro do valor estimado.
- Campo para observações.
- Controle de status do atendimento.
- Listagem dos agendamentos em ordem cronológica.
- Atualização da data de um agendamento.
- Exclusão de agendamentos.

Os status previstos no banco são:

- Agendado
- Em Andamento
- Concluído
- Cancelado

### 📊 Dashboard
O painel inicial foi planejado para apresentar:

- Quantidade total de clientes.
- Quantidade total de veículos.
- Quantidade total de agendamentos.
- Próximos serviços agendados.
- Informações relacionadas aos clientes e veículos.

**Observação:** essas são as funcionalidades previstas no guia. A disponibilidade de cada uma depende de os respectivos arquivos, páginas HTML, estilos e conexões estarem implementados e testados.

## 🗄️ Banco de dados

O banco de dados utilizado no guia recebe o nome `saep_db`.

Ele contém quatro tabelas principais:

| Tabela | Descrição |
|---|---|
| `usuarios` | Armazena os usuários autorizados a acessar o sistema |
| `clientes` | Armazena os dados dos clientes |
| `veiculos` | Armazena os veículos vinculados aos clientes |
| `agendamentos` | Armazena os serviços agendados |

### Relacionamentos

- Um cliente pode possuir vários veículos.
- Um cliente pode ter vários agendamentos.
- Um veículo pode estar associado a vários agendamentos.
- As chaves estrangeiras ajudam a manter a integridade dos relacionamentos.

O script SQL também define índices para auxiliar determinadas consultas.

### Estrutura básica das tabelas

**Usuários**
- Identificador.
- Nome.
- Login.
- Hash da senha.
- Cargo.
- Situação da conta.
- Data de criação.

**Clientes**
- Identificador.
- Nome.
- CPF.
- Hash do CPF.
- Telefone.
- E-mail.
- Endereço.
- Data de cadastro.

**Veículos**
- Identificador.
- Identificador do cliente.
- Placa.
- Marca.
- Modelo.
- Ano.
- Cor.
- Quilometragem.

**Agendamentos**
- Identificador.
- Cliente relacionado.
- Veículo relacionado.
- Data do atendimento.
- Descrição do serviço.
- Status.
- Valor estimado.
- Observações.

## 📂 Estrutura de pastas

A estrutura de referência do guia é:

```text
arquivo oficial/
├── saep_db.sql
└── sistema/
    ├── requirements.txt
    ├── app.py
    ├── banco.py
    ├── autenticacao.py
    ├── clientes.py
    ├── veiculos.py
    ├── agendamento.py
    ├── rotas.py
    ├── templates/
    │   ├── base.html
    │   ├── login.html
    │   ├── dashboard.html
    │   ├── clientes.html
    │   ├── veiculos.html
    │   └── agendamentos.html
    └── static/
        ├── css/
        │   └── style.css
        └── js/
            └── main.js
```

**Atenção à sua versão:** na imagem enviada durante o desenvolvimento, a pasta aparece como `arquivos_oficina`, contendo uma pasta interna com o mesmo nome, além de `db.sql`, `requirements.txt` e alguns módulos Python. O exemplo acima representa a organização proposta pelo guia; não significa que todos esses arquivos já existam na sua pasta.

## 💻 Requisitos para executar o projeto

Antes de iniciar, verifique se o computador possui:

- Python instalado.
- MySQL instalado e em execução.
- Um editor de código, como o Visual Studio Code.
- A extensão Python para VS Code.
- Os arquivos do projeto.
- Acesso ao terminal integrado.

O guia utiliza estas dependências:

```text
Flask==3.0.3
mysql-connector-python==8.4.0
bcrypt==4.1.3
Werkzeug==3.0.3
```

## 🚀 Instalação e execução

### 1. Abrir o projeto

Abra no Visual Studio Code a pasta que contém os arquivos do sistema.

Abra o terminal integrado pelo menu **Terminal → Novo Terminal**.

### 2. Criar o ambiente virtual

Execute:

```powershell
python -m venv venv
```

O ambiente virtual mantém as bibliotecas do projeto isoladas de outras instalações Python.

### 3. Ativar o ambiente virtual no Windows

```powershell
.\venv\Scripts\Activate.ps1
```

Se a ativação funcionar, o terminal normalmente mostrará `(venv)` no início da linha.

### 4. Instalar as dependências

Na estrutura de referência do guia, execute:

```powershell
python -m pip install -r sistema/requirements.txt
```

Se o seu terminal já estiver dentro da pasta que contém `requirements.txt`, utilize:

```powershell
python -m pip install -r requirements.txt
```

Use apenas o comando correspondente à localização real do arquivo.

### 5. Criar o banco de dados

Na estrutura de referência, o arquivo SQL fica na raiz do projeto e se chama `saep_db.sql`.

Abra o MySQL ou o phpMyAdmin e execute o conteúdo desse arquivo para criar o banco e as tabelas.

Na sua pasta atual, o arquivo aparece como `db.sql`. Confira se ele contém o script correto antes de executá-lo.

**Importante:** o script do guia contém comandos `DROP TABLE`, que removem tabelas existentes antes de recriá-las. Isso pode apagar os dados dessas tabelas. Faça uma cópia de segurança e não execute esse script sobre dados que deseja preservar.

### 6. Testar a conexão com o banco

Na estrutura de referência:

```powershell
python sistema/banco.py
```

O arquivo `banco.py` deve tentar conectar ao MySQL e apresentar uma mensagem de sucesso ou de falha.

Se a conexão falhar, verifique se o MySQL está ativo, se o nome do banco está correto e se o usuário e a senha correspondem à sua instalação.

### 7. Iniciar a aplicação

Na estrutura de referência:

```powershell
python sistema/app.py
```

Se o servidor iniciar corretamente, o guia prevê o acesso local pelo endereço:

**http://127.0.0.1:5000**

Para encerrar o servidor, volte ao terminal e pressione `Ctrl + C`.

> Os caminhos dos comandos dependem da estrutura de pastas utilizada. Como sua pasta atual é diferente da estrutura de referência, ajuste os caminhos para a localização real dos arquivos.

## 🧪 Roteiro de testes

Antes de considerar o sistema finalizado, teste cada parte.

### Banco de dados
- [ ] O MySQL está em execução.
- [ ] O banco `saep_db` existe.
- [ ] As quatro tabelas foram criadas.
- [ ] As chaves estrangeiras estão configuradas.
- [ ] O arquivo `banco.py` consegue conectar ao banco.

### Autenticação
- [ ] A tela de login abre.
- [ ] Usuários válidos conseguem entrar.
- [ ] Senhas incorretas são rejeitadas.
- [ ] Usuários inativos não conseguem acessar o sistema.
- [ ] O logout encerra a sessão.
- [ ] A expiração da sessão é verificada.

### Clientes
- [ ] O cadastro funciona.
- [ ] O CPF com quantidade incorreta de dígitos é rejeitado.
- [ ] A busca retorna os registros esperados.
- [ ] A edição salva as alterações.
- [ ] A exclusão funciona.

### Veículos
- [ ] O veículo é vinculado a um cliente existente.
- [ ] A placa duplicada é rejeitada pelo banco.
- [ ] A listagem apresenta os dados corretos.
- [ ] A edição e a exclusão funcionam.

### Agendamentos
- [ ] É possível cadastrar um agendamento.
- [ ] O cliente e o veículo relacionados são apresentados corretamente.
- [ ] A listagem aparece em ordem cronológica.
- [ ] O reagendamento salva a nova data.
- [ ] Os status são apresentados corretamente.

### Interface
- [ ] Todas as páginas HTML necessárias existem.
- [ ] Os links de navegação funcionam.
- [ ] O CSS é carregado corretamente.
- [ ] O JavaScript funciona sem erros.
- [ ] As mensagens de sucesso e erro são exibidas.

## 🔒 Segurança e proteção de dados

O projeto prevê mecanismos de autenticação e tratamento de dados pessoais, incluindo:

- Hash de senhas com Bcrypt.
- Hash do CPF, conforme o guia.
- Consultas SQL parametrizadas nos módulos que as utilizam.
- Controle de sessão.
- Relacionamentos com chaves estrangeiras.
- Validação dos dados recebidos nos formulários.

O uso de hash não é o mesmo que criptografia reversível. Um CPF armazenado somente como hash não pode ser recuperado diretamente a partir desse valor; por isso, o sistema precisa definir como fará consultas e verificações que dependam do CPF original.

Para uso real, também é necessário revisar as permissões de acesso, a proteção de dados pessoais, as configurações de sessão e o tratamento de erros. As credenciais de exemplo do guia devem ser verificadas antes de utilizar o sistema.

## 📚 Organização do desenvolvimento

O guia organiza a implementação nas seguintes fases:

1. Criação da estrutura de pastas.
2. Configuração do ambiente Python e dependências.
3. Criação do banco de dados relacional.
4. Conexão com o MySQL.
5. Implementação da autenticação.
6. Implementação do módulo de clientes.
7. Implementação do módulo de veículos.
8. Implementação do módulo de agendamentos.
9. Criação do controlador de rotas.
10. Configuração da aplicação principal.
11. Desenvolvimento da interface HTML, CSS e JavaScript.
12. Testes e validação das regras de negócio.

Essa divisão permite desenvolver e testar o projeto por etapas, facilitando a identificação de erros e a manutenção do código.

## 🎓 Finalidade acadêmica

Este projeto tem finalidade educacional e está relacionado aos conteúdos de Desenvolvimento de Sistemas, banco de dados, programação web, organização de código, autenticação, validação e testes.

O desenvolvimento permite praticar a integração entre backend, frontend e banco de dados em uma aplicação voltada a uma situação real de gerenciamento.

## 👨‍💻 Autor

**Pedro Henrique Gonzaga Castro**

Estudante de Desenvolvimento de Sistemas.

Projeto desenvolvido para fins acadêmicos, com base no roteiro de implementação SAEP/SENAI.

---

**Status do projeto:** em desenvolvimento. As funcionalidades descritas neste README representam o escopo previsto no guia e devem ser confirmadas por meio da implementação e dos testes.

**Tecnologias principais:** Python, Flask, MySQL, Bcrypt, HTML5, CSS3 e JavaScript.
