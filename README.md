# WorkflowTrackingSystem# Workflow Tracking System

This is a .NET 8 Web API project for managing workflows and processes, with validation and tracking.

## Setup
1. Clone the repo.
2. Restore packages: `dotnet restore`.
3. Update appsettings.json with connection string if needed (default: SQLite file in bin).
4. Run migrations: `dotnet ef migrations add InitialCreate --project WorkflowTrackingSystem.Infrastructure --startup-project WorkflowTrackingSystem.API`
5. Update database: `dotnet ef database update --project WorkflowTrackingSystem.Infrastructure --startup-project WorkflowTrackingSystem.API`
6. Run: `dotnet run --project WorkflowTrackingSystem.API`

## Endpoints
- POST /v1/workflows: Create workflow.
- PUT /v1/workflows/{id}: Update workflow.
- GET /v1/workflows: Get all workflows.
- GET /v1/workflows/{id}: Get workflow by ID.
- POST /v1/processes/start: Start process.
- POST /v1/processes/execute: Execute step.
- GET /v1/processes: Get processes (filters: workflow_id, status, assigned_to).

## Architecture
- Domain: Entities.
- Application: Services, DTOs.
- Infrastructure: DB, repos, validation.
- API: Controllers.

## Validation
For "Finance Approval", simulates external API call to https://jsonplaceholder.typicode.com/todos/1. Logs in console and DB (ProcessLog table).
