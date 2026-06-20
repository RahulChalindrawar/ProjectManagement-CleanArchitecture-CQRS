# Project Management

## Overview
The **Project Management** is a modular and scalable solution designed to manage projects, phasegates, and action items efficiently. It follows **Clean Architecture** principles to ensure maintainability, testability, and separation of concerns. The solution integrates with Azure Cosmos DB for data storage and provides robust role-based authorization mechanisms.

---

## Getting Started

### Prerequisites
- **.NET 8 SDK**: Ensure you have the latest .NET 8 SDK installed.
- **Azure Cosmos DB**: A Cosmos DB instance is required for data storage.
- **Visual Studio 2022**: Recommended IDE for development.

### Installation

1. Navigate to the project directory:
   ```bash
   cd ProjectManagement
   ```
2. Restore NuGet packages:
   ```bash
   dotnet restore
   ```
3. Update the `appsettings.Development.json` file with your Cosmos DB connection string and other configurations.

### Running the Application
1. Build the solution:
   ```bash
   dotnet build
   ```	
2. Run the application:
   ```bash
   dotnet run
   ```
3. Access the API at `https://localhost:<port>`.

---

## Architecture
The solution is built using **Clean Architecture**, which ensures a clear separation of concerns:
- **Domain Layer**: Contains core business logic and entities like `ActionItemDocument` and `UserDocument`.
- **Application Layer**: Implements use cases and business rules, such as `CreateActionItemCommandHandler`.
- **Infrastructure Layer**: Handles external concerns like database access (`ActionItemRepository`) and authorization (`ValidUserWithRoleHandler`).
- **API Layer**: Exposes RESTful endpoints via controllers like `ActionItemsController` and `ProjectsController`.

### Key Principles
- **Dependency Inversion**: High-level modules depend on abstractions, not concrete implementations.
- **Separation of Concerns**: Each layer has a distinct responsibility.

---

## Design Patterns
The solution employs several design patterns:
1. **Repository Pattern**: Abstracts database operations (e.g., `ActionItemRepository`).
2. **Command Pattern**: Encapsulates actions like creating an action item (`CreateActionItemCommand`).
3. **Query Pattern**: Retrieves data based on specific criteria (`GetActionItemsAsync`).
4. **Handler Pattern**: Implements custom authorization logic (`ValidUserWithRoleHandler`).
5. **Mapper Pattern**: Maps data between layers (`CreateActionItemCommandMapper`).
6. **Mediator Pattern**: Decouples request handling using MediatR (`sender.Send(command)`).
7. **Strategy Pattern**: Implements role-based access control (`ConventionalRoleService`).

---

## Technology Used
- **.NET 8**: Modern, high-performance framework for building scalable applications.
- **Azure Cosmos DB**: NoSQL database for storing project and action item data.
- **ASP.NET Core**: Framework for building RESTful APIs.
- **MediatR**: Library for implementing the mediator pattern.
- **FluentValidation**: Library for validating input models.

---

## External NuGet Packages
The solution uses the following NuGet packages:
1. **Microsoft.Azure.Cosmos**: For interacting with Azure Cosmos DB.
2. **MediatR**: For implementing the mediator pattern.
3. **FluentValidation.DependencyInjectionExtensions**: For input validation.

---

## Build and Test
### Building the Solution
Run the following command to build the solution:
```bash
dotnet build
```

### Running Tests
The solution includes unit tests to ensure code quality. Run the tests using:
```bash
dotnet test
```

   
   
