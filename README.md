<div align="center">

# LunaSpaceX ✨

[![.NET 6.0](https://img.shields.io/badge/.NET-6.0-512BD4?style=flat-square&logo=dotnet)](https://dotnet.microsoft.com/download/dotnet/6.0)
[![ASP.NET Core](https://img.shields.io/badge/ASP.NET%20Core-6.0-512BD4?style=flat-square&logo=dotnet)](https://dotnet.microsoft.com)
[![C# 10](https://img.shields.io/badge/C%23-10.0-239120?style=flat-square&logo=csharp)](https://docs.microsoft.com/en-us/dotnet/csharp/)
[![SQL Server](https://img.shields.io/badge/SQL%20Server-2019+-CC2927?style=flat-square&logo=microsoftsqlserver)](https://www.microsoft.com/en-us/sql-server/)
[![License](https://img.shields.io/badge/license-MIT-green?style=flat-square)](LICENSE)

A modern, enterprise-grade inventory and stock management system built with ASP.NET Core Razor Pages. LunaSpaceX provides multi-location store support with comprehensive CRUD operations, user authentication, and real-time inventory tracking.

</div>

---

## 🚀 Features

### Core Capabilities
- **Multi-Location Store Management**: Support for multiple physical locations (Rangsit, Siam, etc.)
- **Inventory Tracking**: Real-time stock monitoring and management
- **User Authentication**: Integrated ASP.NET Core Identity with secure account management
- **Responsive UI**: Bootstrap-based responsive design for desktop and mobile
- **Database-First Architecture**: Entity Framework Core with SQL Server integration
- **RESTful CRUD Operations**: Create, Read, Update, Delete operations for all entities

### Technical Highlights
- ✅ Built on **.NET 6.0** LTS framework
- ✅ **Razor Pages** for clean, maintainable server-side rendering
- ✅ **Entity Framework Core** with SQL Server provider
- ✅ **ASP.NET Core Identity** for authentication & authorization
- ✅ **Bootstrap 4/5** for responsive styling
- ✅ **jQuery Validation** for client-side form validation
- ✅ **Scoped CSS** for component-level styling

## 📋 Table of Contents

- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Configuration](#configuration)
- [Running the Application](#running-the-application)
- [Architecture](#architecture)
- [Database](#database)
- [API Endpoints](#api-endpoints)
- [Development](#development)
- [Contributing](#contributing)
- [License](#license)

## 📦 Prerequisites

Before you begin, ensure you have the following installed:

- **.NET SDK 6.0** or higher ([Download](https://dotnet.microsoft.com/download/dotnet/6.0))
- **SQL Server 2019** or later (or Azure SQL Database)
- **Visual Studio 2022** / **VS Code** with C# extension
- **Git** for version control

### System Requirements
- **OS**: Windows 10/11, macOS, or Linux
- **RAM**: 4GB minimum (8GB recommended)
- **Disk Space**: 500MB+ for development environment

## 🔧 Installation

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/LunaSpaceX.git
cd LunaSpaceX
```

### 2. Restore NuGet Packages

```bash
dotnet restore
```

### 3. Configure Database Connection

Edit `appsettings.json` or `appsettings.Development.json`:

```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=YOUR_SERVER;Database=YOUR_DATABASE;Trusted_Connection=True;MultipleActiveResultSets=true"
  }
}
```

For **Azure SQL Database**:
```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=tcp:your-server.database.windows.net,1433;Initial Catalog=your-database;Persist Security Info=False;User ID=your-username;Password=your-password;MultipleActiveResultSets=False;Encrypt=True;TrustServerCertificate=False;Connection Timeout=30;"
  }
}
```

### 4. Apply Database Migrations

```bash
dotnet ef database update
```

### 5. Build the Solution

```bash
dotnet build
```

## 📁 Project Structure

```
LunaSpaceX/
├── Pages/                           # Razor Pages views and logic
│   ├── Shared/                      # Shared layouts and partials
│   │   ├── _Layout.cshtml           # Master layout template
│   │   ├── _Layout.cshtml.css       # Scoped layout styles
│   │   └── _LoginPartial.cshtml     # Authentication UI partial
│   ├── Rangsit/                     # Rangsit store inventory pages
│   │   ├── IndexRangsit.cshtml(.cs) # Stock listing
│   │   ├── CreateRangsit.cshtml(.cs)# New stock form
│   │   ├── EditRangsit.cshtml(.cs)  # Edit stock form
│   │   └── DeleteRangsit.cshtml     # Delete confirmation
│   ├── Siam/                        # Siam store inventory pages
│   │   ├── IndexSiam.cshtml(.cs)    # Stock listing
│   │   ├── CreateSiam.cshtml(.cs)   # New stock form
│   │   ├── EditSiam.cshtml(.cs)     # Edit stock form
│   │   └── DeleteSiam.cshtml        # Delete confirmation
│   ├── Index.cshtml(.cs)            # Homepage
│   ├── Privacy.cshtml(.cs)          # Privacy policy
│   └── Error.cshtml(.cs)            # Error page
├── Data/                            # Data access layer
│   ├── ApplicationDbContext.cs      # EF Core DbContext
│   └── Migrations/                  # Database migration scripts
├── Areas/                           # Feature areas
│   └── Identity/                    # ASP.NET Core Identity pages
├── Properties/
│   ├── launchSettings.json          # Launch profile configuration
│   ├── serviceDependencies.json     # Service dependencies
│   └── serviceDependencies.local.json
├── wwwroot/                         # Static assets
│   ├── css/                         # Stylesheets
│   │   └── site.css                 # Global styles
│   ├── js/                          # JavaScript files
│   │   └── site.js                  # Global scripts
│   ├── libs/                        # Third-party libraries
│   │   ├── bootstrap/               # Bootstrap framework
│   │   ├── jquery/                  # jQuery library
│   │   └── jquery-validation/       # Client-side validation
│   └── imgs/                        # Images and assets
├── Program.cs                       # Application entry point & configuration
├── LunaSpaceX.csproj               # Project file (.NET configuration)
├── LunaSpaceX.sln                  # Solution file
├── appsettings.json                # Production configuration
├── appsettings.Development.json    # Development configuration
└── README.md                        # This file
```

## ⚙️ Configuration

### Application Settings

**appsettings.json** (Production):
```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Production connection string here"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*"
}
```

**appsettings.Development.json** (Development):
```json
{
  "ConnectionStrings": {
    "DefaultConnection": "Server=(localdb)\\mssqllocaldb;Database=aspnet-LunaSpaceX-dev;Trusted_Connection=True;"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Debug",
      "Microsoft.AspNetCore": "Debug"
    }
  }
}
```

### Authentication Configuration

The application uses ASP.NET Core Identity with the following configuration in `Program.cs`:

```csharp
builder.Services.AddDefaultIdentity<IdentityUser>(options => 
    options.SignIn.RequireConfirmedAccount = true)
    .AddEntityFrameworkStores<ApplicationDbContext>();
```

**Key Settings**:
- Email confirmation required for new accounts
- Password complexity enforced by Identity defaults
- Session timeout configurable per deployment

## 🚀 Running the Application

### Development Mode

```bash
dotnet run --configuration Development
```

The application will be available at:
- **HTTP**: `http://localhost:5000`
- **HTTPS**: `https://localhost:5001`

### Production Mode

```bash
dotnet run --configuration Release
```

### Using Visual Studio

1. Set `LunaSpaceX` as the startup project
2. Select your desired configuration (Debug/Release)
3. Press `F5` to run with debugging, or `Ctrl+F5` without debugging

### Docker Deployment (Optional)

Create a `Dockerfile`:

```dockerfile
FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS runtime
WORKDIR /app
COPY bin/Release/net6.0/publish .
EXPOSE 80 443
ENTRYPOINT ["dotnet", "LunaSpaceX.dll"]
```

Build and run:
```bash
docker build -t lunaspacex:latest .
docker run -p 80:80 -p 443:443 lunaspacex:latest
```

## 🏗️ Architecture

### Design Patterns

- **Razor Pages Pattern**: Page-per-feature organization with code-behind models
- **Repository-like Pattern**: Direct database queries via EF Core DbContext
- **Dependency Injection**: Built-in .NET DI container for service registration
- **Identity-based Authorization**: Claims-based access control

### Layering

```
┌─────────────────────────────────────┐
│   Presentation Layer (Razor Pages)  │
│   - Views (.cshtml)                 │
│   - Page Models (.cshtml.cs)        │
└─────────────────────────────────────┘
           ↓
┌─────────────────────────────────────┐
│   Application Layer                 │
│   - Page Handlers (OnGet, OnPost)   │
│   - Business Logic                  │
└─────────────────────────────────────┘
           ↓
┌─────────────────────────────────────┐
│   Data Access Layer (EF Core)       │
│   - ApplicationDbContext            │
│   - DbSet<T> entities               │
└─────────────────────────────────────┘
           ↓
┌─────────────────────────────────────┐
│   Data Storage (SQL Server)         │
│   - Stocks table                    │
│   - Identity tables                 │
└─────────────────────────────────────┘
```

## 🗄️ Database

### Entity Schema

The application uses the following primary entities:

**Stocks Table**:
```sql
CREATE TABLE stocks (
    itemid INT PRIMARY KEY IDENTITY(1,1),
    item NVARCHAR(MAX),
    storeid INT,
    supplier NVARCHAR(MAX),
    [...]
);
```

**Store Locations**:
- `storeid = 1`: Rangsit
- `storeid = 2`: Siam

### Migrations

View all applied migrations:
```bash
dotnet ef migrations list
```

Create a new migration:
```bash
dotnet ef migrations add YourMigrationName
```

Apply pending migrations:
```bash
dotnet ef database update
```

Rollback last migration:
```bash
dotnet ef database update PreviousMigrationName
```

## 🔌 API Endpoints

### Stock Management

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/Rangsit` | List all Rangsit stocks |
| `GET` | `/Siam` | List all Siam stocks |
| `GET` | `/Rangsit/Create` | Show create form (Rangsit) |
| `POST` | `/Rangsit/Create` | Create new stock (Rangsit) |
| `GET` | `/Rangsit/Edit/{id}` | Show edit form (Rangsit) |
| `POST` | `/Rangsit/Edit/{id}` | Update stock (Rangsit) |
| `GET` | `/Rangsit/Delete/{id}` | Show delete confirmation |
| `POST` | `/Rangsit/Delete/{id}` | Delete stock |

Similar endpoints exist for `/Siam/*`

### Authentication

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/Identity/Account/Login` | Login page |
| `POST` | `/Identity/Account/Login` | Submit login |
| `GET` | `/Identity/Account/Register` | Registration page |
| `POST` | `/Identity/Account/Register` | Create account |
| `POST` | `/Identity/Account/Logout` | Logout user |

### General

| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET` | `/` | Homepage |
| `GET` | `/Privacy` | Privacy policy |
| `GET` | `/Error` | Error page |

## 👨‍💻 Development

### Code Style & Conventions

- **C# Naming**: PascalCase for public members, camelCase for local variables
- **File Organization**: One class per file
- **Indentation**: 4 spaces
- **Async/Await**: Use async patterns for I/O operations

### Building from Source

```bash
# Clean previous builds
dotnet clean

# Restore dependencies
dotnet restore

# Build the solution
dotnet build

# Run tests (if any)
dotnet test

# Package for release
dotnet publish -c Release -o ./publish
```

### Debugging

**Visual Studio**: 
- Set breakpoints (F9)
- Run with debugging (F5)
- Step through code (F10/F11)

**VS Code**:
- Install C# extension
- Create `.vscode/launch.json`
- Press F5 to start debugging

### Useful Commands

```bash
# Check for .NET CLI tools
dotnet tool list -g

# Update .NET CLI tools
dotnet tool update -g dotnet-ef

# Analyze project structure
dotnet sln list

# View project dependencies
dotnet list reference
```

## 🤝 Contributing

We welcome contributions from the community! Here's how to get started:

### Before You Begin
1. **Fork** the repository
2. **Clone** your fork locally
3. **Create** a new feature branch: `git checkout -b feature/your-feature-name`

### Development Workflow

```bash
# Create feature branch
git checkout -b feature/amazing-feature

# Make your changes
# Write clean, well-documented code
# Test thoroughly

# Commit with clear messages
git commit -m "feat: add amazing feature"

# Push to your fork
git push origin feature/amazing-feature

# Create a Pull Request on GitHub
```

### Commit Message Conventions

Follow [Conventional Commits](https://www.conventionalcommits.org/):

```
feat: add new inventory filter
fix: resolve stock update bug
docs: update database schema docs
refactor: simplify database query logic
test: add tests for stock CRUD operations
```

### Code Review Process

1. Ensure all tests pass
2. Follow project code style
3. Add/update documentation as needed
4. Respond to review feedback
5. Merge after approval

## 📄 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

MIT License permits:
- ✅ Commercial use
- ✅ Modification
- ✅ Distribution
- ✅ Private use

With the conditions:
- 📋 License and copyright notice must be included

## 📞 Support & Contact

- **Issues**: [GitHub Issues](https://github.com/AlphsX/LunaSpaceX/issues)
- **Discussions**: [GitHub Discussions](https://github.com/AlphsX/LunaSpaceX/discussions)

## 🗺️ Roadmap

### Planned Features (v2.0)
- [ ] Advanced filtering and search
- [ ] Export to Excel/CSV
- [ ] Mobile app (React Native)
- [ ] Real-time notifications
- [ ] Audit logging
- [ ] API endpoint documentation (Swagger/OpenAPI)
- [ ] Unit and integration tests
- [ ] Docker containerization

### Performance Improvements
- [ ] Query optimization
- [ ] Caching layer (Redis)
- [ ] Pagination for large datasets
- [ ] Async/await patterns throughout

## 📚 Additional Resources

- [ASP.NET Core Documentation](https://docs.microsoft.com/en-us/aspnet/core/)
- [Entity Framework Core](https://docs.microsoft.com/en-us/ef/core/)
- [Razor Pages Guide](https://docs.microsoft.com/en-us/aspnet/core/razor-pages/)
- [ASP.NET Core Identity](https://docs.microsoft.com/en-us/aspnet/core/security/authentication/identity/)
- [.NET Best Practices](https://docs.microsoft.com/en-us/dotnet/fundamentals/code-analysis/style-rules/)

---

<div align="center">

**Built with ❤️ using ASP.NET Core & SQL Server**

⭐ If you find this project helpful, please consider giving it a star!

</div>