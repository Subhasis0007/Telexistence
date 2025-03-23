# Telexistence

## Telexistence Remote Monitoring and Control API

### Introduction
Telexistence provides remote operation services using robots. This project aims to build an API that enables users to interact with a robot for remote monitoring and control.

### Features
- Accepts commands to control the robot (e.g., "move forward", "rotate 90 degrees").
- Exposes the robot’s current status (position, operating task, etc.).
- Supports user authentication and authorization via JWT.
- Deployable to Azure with CI/CD setup for automated deployments.
- Extensible for frontend teams with real-time communication and logging.

### API Endpoints

#### `/command`
- **POST**: Accepts a command to control the robot.
- **PUT**: Updates an existing command.
- **GET**: Retrieves details of a specific command.

#### `/status`
- **GET**: Returns the current status of the robot.

#### `/history`
- **GET**: Returns command history of the robot.

#### `/login`
- **POST**: Accepts username and password, returns an authentication token (JWT).

#### `/health`
- **GET**: Health check endpoint to monitor API availability.

### Example Command Request
```json
{
  "command": "move forward", 
  "robot": "TX-010", 
  "user": "user123"
}
```

### DevOps Setup
- The API is deployed to Azure using an App Service.
- CI/CD is set up using GitHub Actions.
- Infrastructure-as-Code (IaC) is defined using Terraform.
- Logging is handled using Serilog and integrated with Azure Monitor.

#### Deployment Pipeline
1. Code is pushed to GitHub.
2. GitHub Actions build the .NET application.
3. Unit tests are executed.
4. The application is deployed to Azure App Service.
5. A health check is performed.

#### How to Trigger Deployment
- Push a commit to the `main` branch.
- Manually trigger a GitHub Actions workflow (if configured).

### Testing
- Unit tests cover business logic for robot commands and status retrieval.
- A mock database is used for testing within a containerized environment.

#### Running Tests
```sh
cd project_directory
 dotnet test
```

### Future Extensibility
- Designed for easy integration with frontend teams.
- Potential WebSocket integration for real-time communication.
- API documentation provided for frontend consumption.

### Setup and Run Instructions
#### Prerequisites
- .NET 8 SDK
- Azure CLI (for deployment)
- Docker (for running mock database)

#### Running Locally
```sh
git clone https://github.com/your-repo.git
cd project_directory
dotnet restore
dotnet run
```

#### Running with Docker
```sh
docker-compose up --build
```

### Time Breakdown
| Task | Time Spent |
|------|------------|
| Read Documents | 30 mins |
| Write Tests | 2 hours |
| Implement Features | 4 hours |
| Refactor Code | 1 hour |
| Set Up CI/CD | 2 hours |

### Evaluation Criteria
- **Backend Skills**: Clean, modular, and well-structured code following REST principles.
- **DevOps Knowledge**: Understanding and setup of a deployable CI/CD pipeline.
- **Testing**: Unit tests covering key parts of the application.
- **Extensibility**: Scalable code for future enhancements.
- **IaC Competency**: Use of Terraform for defining Azure resources.

### Deliverables
- Source code hosted on GitHub.
- Invite `system-application@tx-inc.com` as a collaborator.
- Functional application ready for deployment.
- Comprehensive documentation including setup, tests, and design decisions.

---
This project lays a foundation for evaluating backend, DevOps, and scalability skills in a real-world Telexistence use case.

