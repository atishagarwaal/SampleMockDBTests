# TodoApp - Mock DB Tests Sample

1. Overview

This repository is a small .NET 10 sample that demonstrates how to write and run unit tests which mock the database layer. The primary goal is to show patterns for mocking DbSet<T> and DbContext using popular libraries (Moq, EF Core InMemory, and EFCore mock helpers).

2. Description

The solution contains a minimal API project and a dedicated test project (TodoApi.StubTests) that illustrates: creating mocked DbSet<T>, setting up async query providers, stubbing FindAsync/SaveChangesAsync, and verifying interactions with the context. Use the tests as examples for writing controller/data-layer unit tests without a real database.

Key libraries used in tests:

- Moq
- Microsoft.EntityFrameworkCore.InMemory
- EFCore.Mock
- EntityFrameworkCoreMock.Moq

3. Pre-requisites

- .NET 10 SDK (install from https://dotnet.microsoft.com)
- Visual Studio 2026 or Visual Studio Code with the C# extension
- Git

4. Build and Run

From the repository root (where TodoApp.sln is located):

- Restore and build the solution:

  dotnet restore
  dotnet build TodoApp.sln

- Run the sample API project (if you want to exercise it manually):

  dotnet run --project TodoApi/TodoApi.csproj

- Run the test project that demonstrates mocking:

  dotnet test TodoApi.StubTests/TodoApi.StubTests.csproj

Notes:
- Test code is located under TodoApi.StubTests; open TodoStubTests.cs to see mocking patterns and helpers.
- The tests are designed to run without a real database by using mocks and/or the EF Core InMemory provider.

5. Tests and mock database

This repository includes unit tests that use mocking for the data layer. Key observations:

- The TodoApi.StubTests project uses Moq to create mocked DbSet<T> and a mocked DBContext (see TodoApi.StubTests/TodoStubTests.cs).
- Microsoft.EntityFrameworkCore.InMemory is referenced by TodoApi and TodoApi.Data for in-memory EF Core provider.
- Additional test helpers referenced: EFCore.Mock and EntityFrameworkCoreMock.Moq in TodoApi.StubTests.

To run the test project with mocks:

  dotnet test TodoApi.StubTests/TodoApi.StubTests.csproj

These tests are designed to exercise controllers and data access logic without requiring a real database.
