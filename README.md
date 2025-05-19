# 🛵 TrackZone API

API RESTful desenvolvida com ASP.NET Core para gerenciamento de motos em pátios de filiais. O sistema permite o cadastro de filiais, login, check-in e check-out de motos, com integração ao banco Oracle, documentação via Swagger e organização por plano cartesiano.

---

## ✅ Funcionalidades

- Cadastro e login de filiais
- Registro e consulta de motos
- Check-in e check-out de motos
- Dashboard com status da operação
- Integração com Oracle via Entity Framework Core
- Swagger UI para documentação
- Mapeamento via Fluent API

---

## 🧠 Tecnologias Utilizadas

- ASP.NET Core 7.0+
- Entity Framework Core
- Banco de Dados Oracle
- Swagger/OpenAPI
- Fluent API (Mappings)
- C#

---

## 📁 Estrutura do Projeto

```
WebApplication1/
│
├── Models/
│ ├── Filial.cs
│ ├── Moto.cs
│ ├── CheckIn.cs
│ ├── CheckOut.cs
│ ├── LoginDto.cs
│ └── RegisterFilialDto.cs
│
├── Controllers/
│ ├── AuthController.cs
│ ├── MotoController.cs
│ └── CheckController.cs
│
├── Data/
│ └── Mappings/
│ ├── FilialMapping.cs
│ ├── MotoMapping.cs
│ ├── CheckInMapping.cs
│ └── CheckOutMapping.cs
│
├── Connection/
│ └── AppDbContext.cs
│
├── appsettings.json
└── Program.cs
```


---

## ⚙️ Como Executar o Projeto

1. Clone o repositório:
```
   git clone https://github.com/seu-usuario/seu-repositorio.git
```
2. Configure o appsettings.json com sua connection string Oracle:
  ```
  "ConnectionStrings": {
  "OracleConnection": "User Id=seu_usuario;Password=sua_senha;Data Source=localhost:1521/XE;"
}

  ```
3. Instale os pacotes NuGet necessários:
```
Install-Package Oracle.EntityFrameworkCore
Install-Package Microsoft.EntityFrameworkCore.Design

```

4. Crie as tabelas no banco:
```
Add-Migration CreateMottuTrackTables
Update-Database

```

5. Execute a aplicação:
```
dotnet run
```

6. Acesse a documentação Swagger
```
https://localhost:{porta}/swagger

```

---

```
🔗 Principais Rotas da API
🔐 Autenticação
| Método | Rota               | Descrição               |
| ------ | ------------------ | ----------------------- |
| POST   | /api/auth/cadastro | Cadastro de nova filial |
| POST   | /api/auth/login    | Login de filial         |


🛵 Motos
| Método | Rota                        | Descrição                  |
| ------ | --------------------------- | -------------------------- |
| GET    | /api/moto                   | Lista todas as motos       |
| GET    | /api/moto/{id}              | Busca moto por ID          |
| GET    | /api/moto/filial/{filialId} | Lista motos por filial     |
| POST   | /api/moto                   | Cadastra nova moto         |
| PUT    | /api/moto/{id}              | Atualiza dados de uma moto |
| DELETE | /api/moto/{id}              | Remove uma moto            |


🧾 Check-in / Check-out
| Método | Rota                | Descrição                 |
| ------ | ------------------- | ------------------------- |
| POST   | /api/check/checkin  | Realiza check-in da moto  |
| POST   | /api/check/checkout | Realiza check-out da moto |

```

---

## 📦 Migrations
* Para criar o banco de dados com EF Core e Oracle:
```
Add-Migration CreateMottuTrackTables
Update-Database

```

## 📊 Exemplo de Dashboard (API)
* Você pode implementar futuramente endpoints como:
```
GET /api/dashboard/{filialId}

```
* E retornar um resumo como:
```
{
  "totalMotos": 18,
  "motosDisponiveis": 10,
  "emManutencao": 4,
  "alugadas": 2,
  "checkinsHoje": 3,
  "checkoutsHoje": 2,
  "recentes": [ ... ]
}

```

---

## 👥 Desenvolvedores

- Leticia Cristina Dos Santos Passos RM: 555241
- André Rogério Vieira Pavanela Altobelli Antunes RM: 554764
- Enrico Figueiredo Del Guerra RM: 558604







