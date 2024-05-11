# Tutorial: Create a web API with ASP.NET Core

- https://learn.microsoft.com/en-us/aspnet/core/tutorials/first-web-api?view=aspnetcore-8.0&tabs=visual-studio

# Overview

1. GET /api/TodoItems
2. GET /api/TodoItems/{id}
3. POST /api/TodoItems
4. PUT /api/TodoItems/{id}
5. DELETE /api/TodoItems/{id}

# Prerequisites

1. Visual Studio Code
2. C# for Visual Studio Code (latest version)
3. .NET 8.0 SDK

## Create a web project

1. Create Web API by Swagger

```sh
dotnet new webapi --use-controllers -o api
cd api
dotnet add package Microsoft.EntityFrameworkCore.InMemory
code -r ../api
```

2. Hot reload enabled. supported to http://localhost:<port>/swagger/index.html

```sh
dotnet watch run
```

## ASP.NET Core - Web API Structure

1. Main - Program.cs
2. If will change "Port" to launchSettings.json (http, https)

## Extensions

1. C# Dev Kit
2. .NET Install Tool
3. .NET Extension Pack
4. Nuget Gallery
5. Prettier - Code Formatter
6. C# Extensions

## Add Package by NuGet Open

- api.csproj

1. Microsoft.EntityFrameworkCore.SqlServer
2. Microsoft.EntityFrameworkCore.Tools
3. Microsoft.EntityFrameworkCore.Design

- create a class by New C# Extensions
- create constructor by ctor
- create property by prop

4. setup "ConnectionStrings" application.json

```json
{
  ...
  "ConnectionStrings": {
    "DefaultConnection": "DATA Source=BUMBIM\\SQLEXPRESS;Initial Catalog=Sharkfin;Integrated Security=True;Connect Timeout=30;Encrypt=True;TrustServerCertificate=True;ApplicationIntent=ReadWrite;MultiSubnetFailover=False"
  }
  ...
}
```

```c#
<PropertyGroup>
  ...
  <InvariantGlobalization>false</InvariantGlobalization>
  ...
</PropertyGroup>

```

```sh
dotnet ef migrations add Init

# Use when updated database _context
dotnet ef database update
```

5. SSMS Created tables (auto by ef database update)

\_\_EFMigrationsHistory
Comments
Stocks

- Migrations (auto in VSCode)

## Controllers

StockController.cs

## Data Transfer Object (DTOs)

1. dto is that anything in programming

- ตัวอย่าง: ผู้ใช้ป้อนข้อมูล
  {
  username: "taddysmith",
  password: "IceSpice22"
  }
  -> ผ่าน DTO -> Response:
  {
  username: "teddy"
  }
- ตัวอย่าง: Request
  Model
  [Required]
  public Password { get; set; }

2. Create folder Dtos

- Stock/StockDto.cs
- Comment/CommentDto.cs

3. Create folder Mappers

- Stock/StockMappers.cs
- Comment/CommentMappers.cs
