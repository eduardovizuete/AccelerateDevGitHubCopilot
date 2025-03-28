# Library App

## Description

The **Library App** is a console-based application designed to manage a library system. It allows users to search for patrons, view and manage loans, and renew memberships. The application uses JSON files as its data store and follows a modular architecture with dependency injection for flexibility and testability.

## Project Structure

The repository is organized as follows:

- **AccelerateDevGitHubCopilot.sln**: Solution file for the project.
- **src**: Contains the source code for the application.
  - **Library.ApplicationCore**: Core application logic and domain entities.
    - `Entities/`: Domain models such as `Author`, `Book`, `Loan`, and `Patron`.
    - `Enums/`: Enumerations for statuses like `LoanExtensionStatus` and `MembershipRenewalStatus`.
    - `Interfaces/`: Interfaces for services and repositories.
    - `Services/`: Business logic implementations for loans and patrons.
    - `Library.ApplicationCore.csproj`: Project file for the core library.
  - **Library.Console**: Console application for interacting with the library system.
    - `appSettings.json`: Configuration file for JSON data paths.
    - `CommonActions.cs`: Enum for user actions in the console.
    - `ConsoleApp.cs`: Main application logic for the console interface.
    - `ConsoleState.cs`: Enum for application states.
    - `Json/`: JSON files for storing library data.
    - `Program.cs`: Entry point for the console application.
    - `Library.Console.csproj`: Project file for the console application.
  - **Library.Infrastructure**: Data access layer for interacting with JSON files.
    - `Data/`: Contains classes like `JsonData`, `JsonLoanRepository`, and `JsonPatronRepository`.
    - `Library.Infrastructure.csproj`: Project file for the infrastructure library.
- **tests**: Contains unit tests for the application.
  - **UnitTests**: Unit tests for core services and repositories.
    - `LoanFactory.cs`: Factory for creating test loan objects.
    - `PatronFactory.cs`: Factory for creating test patron objects.
    - `ApplicationCore/`: Tests for core services like `LoanService` and `PatronService`.
    - `UnitTests.csproj`: Project file for the unit tests.

## Key Classes and Interfaces

### Core Classes
- **`Author`**: Represents an author in the library.
- **`Book`**: Represents a book with details like title, genre, and author.
- **`BookItem`**: Represents a physical copy of a book.
- **`Loan`**: Represents a loan of a book item to a patron.
- **`Patron`**: Represents a library patron.

### Enums
- **`LoanExtensionStatus`**: Statuses for extending a loan.
- **`LoanReturnStatus`**: Statuses for returning a loan.
- **`MembershipRenewalStatus`**: Statuses for renewing a patron's membership.

### Interfaces
- **`ILoanRepository`**: Interface for loan data access.
- **`IPatronRepository`**: Interface for patron data access.
- **`ILoanService`**: Interface for loan-related business logic.
- **`IPatronService`**: Interface for patron-related business logic.

### Key Classes
- **`ConsoleApp`**: Main class for the console application, managing user interactions and state transitions.
- **`JsonData`**: Handles loading and saving data to JSON files.
- **`JsonLoanRepository`**: Implements `ILoanRepository` for managing loans.
- **`JsonPatronRepository`**: Implements `IPatronRepository` for managing patrons.
- **`LoanService`**: Implements `ILoanService` for loan-related operations.
- **`PatronService`**: Implements `IPatronService` for patron-related operations.

## Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/library-app.git
   cd library-app
   ```

2. Build the solution:
   ```bash
   dotnet build
   ```

3. Run the application:
   ```bash
   dotnet run --project src/Library.Console/Library.Console.csproj
   ```

4. Use the console interface to:
   - Search for patrons.
   - View and manage loans.
   - Renew memberships.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
