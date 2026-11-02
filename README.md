# 🧾 Register of Products System

Sistema web para **gerenciamento de produtos e usuários**, desenvolvido em C# com ASP.NET Core MVC.

O projeto implementa operações de cadastro e gerenciamento de registros, autenticação de usuários, controle de sessão e perfis de acesso, persistência de dados com Entity Framework Core e SQL Server.

## ⚙️ Funcionalidades

- Cadastro, listagem, edição e exclusão de produtos
- Cadastro e gerenciamento de usuários
- Autenticação de usuários
- Controle de sessão
- Controle de acesso por perfil
- Alteração de senha
- Redefinição de senha com envio por e-mail
- Persistência de dados utilizando Entity Framework Core
- Migrations para controle da estrutura do banco de dados

## 🛠️ Tecnologias

- C#
- ASP.NET Core MVC
- .NET 9
- Entity Framework Core
- SQL Server
- HTML
- CSS
- Bootstrap
- jQuery
- Newtonsoft.Json

## 🚀 Como executar localmente

### Pré-requisitos

- .NET SDK 9
- SQL Server
- Git

### 1. Clone o repositório

```bash
git clone git@github.com:danielfelix45/register-of-products-system-aspnetmvc.git
cd register-of-products-system-aspnetmvc
```

### 2. Configure o banco de dados

A aplicação utiliza a connection string `DataBase`.

Para desenvolvimento local, configure a conexão de acordo com sua instalação do SQL Server. Exemplo:

```json
"ConnectionStrings": {
  "DataBase": "Server=localhost\\SQLEXPRESS;Database=DB_ProductSystem;Trusted_Connection=True;TrustServerCertificate=True"
}
```

### 3. Aplique as migrations

Na pasta do projeto:

```bash
dotnet ef database update
```

### 4. Execute a aplicação

```bash
dotnet run --project RegisterOfProducts
```

A URL utilizada pela aplicação será exibida no terminal.

## 📧 Configuração do SMTP

O projeto utiliza SMTP para o envio de e-mails relacionados à redefinição de senha.

Credenciais reais não devem ser adicionadas ao repositório. Em desenvolvimento, elas podem ser configuradas com **User Secrets** ou variáveis de ambiente.

Exemplo utilizando User Secrets:

```bash
dotnet user-secrets init --project RegisterOfProducts

dotnet user-secrets set "SMTP:UserName" "seu-email" --project RegisterOfProducts
dotnet user-secrets set "SMTP:password" "sua-senha" --project RegisterOfProducts
dotnet user-secrets set "SMTP:Host" "seu-servidor-smtp" --project RegisterOfProducts
```

As demais configurações, como nome e porta do servidor SMTP, devem corresponder ao provedor utilizado.

## 🔐 Segurança das senhas

As senhas não são armazenadas em texto puro.

O projeto utiliza **PBKDF2 com SHA-256**, salt aleatório e múltiplas iterações para derivação do hash. A validação utiliza comparação em tempo constante por meio de `CryptographicOperations.FixedTimeEquals`.

## 🔮 Melhorias futuras

- Tratar os avisos relacionados a nullable references
- Adicionar testes automatizados
- Aprimorar o gerenciamento das configurações por ambiente
- Evoluir o fluxo de recuperação de senha

## 👨‍💻 Autor

**Daniel Félix**

Desenvolvedor Backend | Node.js | TypeScript | C# | APIs REST
