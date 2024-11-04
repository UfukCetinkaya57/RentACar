# RentACar API

RentACar API is a basic ASP.NET Core API project designed to demonstrate modularity and clean architecture in high-performance settings with fundamental endpoints. The project is structured with a clean architecture utilizing best practices like SOLID principles, CQRS, and dependency injection.

### Architecture
The project is designed using **Clean Architecture** and layered structure adhering to SOLID and CQRS principles:
- **Application Layer**: Contains business logic and validation processes.
- **Persistence Layer**: Manages database operations.
- **Domain Layer**: Holds core entities and objects.
- **Web API Layer**: Hosts the API endpoints.

## Technologies Used
- **EF Core**: Entity Framework for database management.
- **MediatR**: Implements the CQRS model.
- **AutoMapper**: Manages object mapping.
- **FluentValidation**: Manages input validation processes.
- **Serilog**: Logs to file and SQL Server.

### Serilog
- **File Logging**: Log files are saved in the directory specified by the `FolderPath` field in `appsettings.json`.
- **SQL Server Logging**: Errors and events are recorded in the `Logs` table on SQL Server.
- **Configuration**: Logging settings can be customized in the `SeriLogConfigurations` section of `appsettings.json`.

## Installation

### Requirements
- [SQL Server](https://www.microsoft.com/sql-server/sql-server-downloads)
- Docker (optional, for working with SQL Server and PostgreSQL)

### Steps
1. Clone the project:
```git clone <repository-url>```

2. Configure database connections:
- Set the RentACar database connection in the `ConnectionStrings` section of `appsettings.json`.

3. Apply migrations and update the database:
```dotnet ef database update ```

5. Start the application:
```dotnet run```
