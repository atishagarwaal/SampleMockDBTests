# TodoApp - API Unit Tests

.NET unit test application to test Web API using MSTest.

## Overview
This repository contains unit tests written in C# using the MSTest framework for testing a Web API (TodoApp). The tests exercise the API's business logic and can be executed using the .NET CLI.

## Prerequisites
- .NET SDK (6.0 or later recommended)
- The repository's solution and test projects restored (dotnet restore)

## Setup
1. Clone the repository:

   git clone https://github.com/atishagarwaal/TodoApp.git
   cd TodoApp

2. Restore dependencies:

   dotnet restore

3. Build the solution (optional):

   dotnet build

## Running the tests
Run all tests in the repository using the .NET CLI:

    dotnet test

To run tests in a specific test project, specify the project path:

    dotnet test ./tests/YourTestProject.csproj

To run a single test by name (using a filter):

    dotnet test --filter "FullyQualifiedName~Namespace.ClassName.MethodName"

## Test framework
- Test framework: MSTest (Microsoft.VisualStudio.TestTools.UnitTesting)
- Test runner: dotnet test

## Typical workflow
- Add or update tests in the test project(s) under the tests/ or src/ folders.
- Run `dotnet test` locally and fix failures before pushing changes.
- Consider adding a CI workflow to run `dotnet test` on pull requests.

## Contributing
Contributions are welcome. Please open issues or pull requests for bug fixes and improvements. Include unit tests for any new behavior.

## License
If this project should have a license, add a LICENSE file to the repository and update this section accordingly.
