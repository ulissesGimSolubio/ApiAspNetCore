# ApiAspNetCore

Implementação de API com **EntityFrameworkCore**, **SQL Server**, **Autenticação com JWT**, **Swagger** e **ASP.NET Core 8.0.3**

![image](https://github.com/ulissesgimenes/ApiAspNetCore/assets/12112777/80b74f04-5eee-4b7c-b61a-7658218b2e42)

---

## 📚 Ementa do curso

### ✅ Módulo 01: Introdução
- ✅ Introdução e pré-requisitos.

### ✅ Módulo 02: Conceitos REST
- ✅ Protocolo HTTP.
- ✅ Códigos de status (100, 200, 300, 400, 500).
- ✅ Histórico REST.
- ✅ Arquitetura REST.
- ✅ Conceituando RESTful.
- ✅ Recursos.
- ✅ Boas práticas.
- ✅ Verbos HTTP: GET, POST, PUT, DELETE.
- ✅ Idempotência (mesmo resultado com múltiplas requisições).

### ✅ Módulo 03: Criando a primeira API
- ✅ Via CLI:
  - `dotnet new list`
  - `dotnet new webapi -h`
  - `dotnet new webapi -n PrimeiraApiCli`
- ✅ Via Visual Studio:
  - Novo projeto Web API.
- ✅ Visão geral de um projeto Web API.

### ✅ Módulo 04: Recursos fundamentais de uma Web API
- ✅ Estrutura `Controller` com `[ApiController]`.
- ✅ Roteamento básico.
- ✅ Action Results e códigos de status:
  - `[HttpPost]`, `[HttpGet]`, `[HttpPut]`, `[HttpDelete]`
- ✅ Documentação com Swagger:
  - `builder.Services.AddSwaggerGen()`
  - `app.UseSwagger()`, `app.UseSwaggerUI()` dentro de `if (app.Environment.IsDevelopment())`
- ✅ Respostas formatadas com `[ProducesResponseType(...)]`
- ✅ Analisadores e convenções:
  - No `.csproj`: `<IncludeOpenApiAnalyzers>true</IncludeOpenApiAnalyzers>`
- ✅ Minimal APIs:
  - CLI: `dotnet new webapi -n MinimalAPI -minimal`
  - Projeto direto na `Program.cs`
  - No Visual Studio: desmarcar a opção "Use controllers"

### ✅ Módulo 05: Operações com banco de dados
- ✅ Criando a entidade `Produto`
- ✅ Configurando EF Core (SQL Server, Design e Tools)
- ✅ Banco de dados:
  - `Add-Migration v1`
  - `Update-Database`
- ✅ Métodos HTTP com `ActionResult`:
  - `[HttpGet]`, `[HttpPost]`, `[HttpPut]`, `[HttpDelete]`
- ✅ Validação de entidade.
- ✅ Boas práticas de implementação.

### ✅ Módulo 06: Segurança

#### 🔐 ASP.NET Identity
- ✅ Instalação:  
  `Install-Package Microsoft.AspNetCore.Identity.EntityFrameworkCore -Version 8.0.3`
- ✅ Configuração no `Program.cs`:
  - `builder.Services.AddIdentity(...)`
  - `app.UseAuthentication()`
- ✅ Alterar o `DbContext` para herdar de `IdentityDbContext`
- ✅ `Add-Migration Identity`
- ✅ `Update-Database`

#### 🔐 JWT - JSON Web Token
- ✅ Classe `JwtSettings`
- ✅ Configuração no `appsettings.json`
- ✅ Instalação:
  `Install-Package Microsoft.AspNetCore.Authentication.JwtBearer -Version 8.0.3`
- ✅ Configuração no `Program.cs`:
  - Após `AddIdentity`, incluir configuração de autenticação
- ✅ Modelos de autenticação
- ✅ `AuthController` com login e registro
- ✅ Integração JWT com Swagger:
  - Configuração em `builder.Services.AddSwaggerGen(...)`

#### ✅ Autenticação e Autorização
- ✅ `[Authorize]`, `[AllowAnonymous]`
- ✅ Autorização por `Roles` (papeis)
- ✅ Visualização do token: [jwt.io](https://jwt.io/)
- ✅ Método `GerarJwt` com inclusão de roles
- ✅ Testes:
  - Role `Admin` no `[HttpDelete]`
  - Role inválida → erro 403

#### ✅ Segurança adicional
- ✅ HTTPS (`app.UseHttpsRedirection()`)
  - Protege contra ataques "Man in the Middle"
- ✅ CORS

#### 🎁 Bônus
- ✅ Otimização da organização do projeto
