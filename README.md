# SpendSmart

SpendSmart is a simple **ASP.NET Core MVC** web application for tracking personal expenses. It was built as a hands-on .NET learning project, covering MVC controllers, Razor views, and Entity Framework Core in a small, easy-to-follow codebase.

## ✨ Features

- **Add an expense** — record a value and a description
- **Edit an expense** — update the value or description of an existing entry
- **Delete an expense** — remove entries you no longer need
- **View all expenses** in a table, along with a running **total**
- Simple, server-rendered UI using Razor views and Bootstrap

## 🛠 Tech Stack

- **.NET 8** / ASP.NET Core MVC
- **Entity Framework Core 9** with the **In-Memory** database provider (no external database setup required)
- Razor views (`.cshtml`) with Bootstrap-based styling

## 📂 Project Structure

```
SpendSmart/
├── Controllers/
│   └── HomeController.cs        # Handles Index, Expenses, Create/Edit/Delete actions
├── Models/
│   ├── Expense.cs                # Expense entity (Id, Value, Description)
│   ├── SpendSmartDbContext.cs    # EF Core DbContext (Expenses DbSet)
│   └── ErrorViewModel.cs         # Standard error view model
├── Views/
│   ├── Home/
│   │   ├── Index.cshtml              # Landing page
│   │   ├── Expenses.cshtml           # Expense list + total
│   │   └── CreateEditExpense.cshtml  # Create / edit form
│   └── Shared/
│       ├── _Layout.cshtml
│       └── Error.cshtml
├── Program.cs                    # App startup & service configuration
└── SpendSmart.csproj
```

## 🗄 Data Model

| Field | Type | Notes |
|---|---|---|
| `Id` | `int` | Primary key |
| `Value` | `decimal` | Expense amount |
| `Description` | `string` | Required — short description of the expense |

Data is stored using EF Core's **in-memory database provider**, which means all expenses reset every time the application restarts — ideal for demos and tutorials, but not for persistent production use.

## 🚦 Application Routes

| Action | Route | Description |
|---|---|---|
| `Index` | `/` | Home/landing page |
| `Expenses` | `/Home/Expenses` | View all expenses and the running total |
| `CreateEditExpense` | `/Home/CreateEditExpense` or `/Home/CreateEditExpense/{id}` | Add a new expense, or edit an existing one by ID |
| `CreateEditExpenseForm` | `/Home/CreateEditExpenseForm` (POST) | Form submission handler for create/edit |
| `DeleteExpense` | `/Home/DeleteExpense/{id}` | Delete an expense by ID |

## 🚀 Getting Started

### Prerequisites

- [.NET 8 SDK](https://dotnet.microsoft.com/download)
- Visual Studio 2022 / Visual Studio Code / JetBrains Rider (any editor with .NET support)

### Running the app

1. Clone the repository
   ```bash
   git clone https://github.com/ruwanyahettiarachchi/SpendSmart-.Net-Tutorial.git
   cd SpendSmart-.Net-Tutorial
   ```
2. Restore dependencies
   ```bash
   dotnet restore
   ```
3. Run the application
   ```bash
   dotnet run
   ```
4. Open your browser at the URL shown in the console (typically `https://localhost:xxxx`), then navigate to **Expenses** to start tracking.

## 📄 License

This project is available for personal and educational use. Feel free to fork and adapt it for your own learning purposes.
