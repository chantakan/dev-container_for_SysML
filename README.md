# SysML Development Environment with VSCode DevContainer

This project sets up a development environment for SysML using VSCode DevContainers. It includes a Jupyter notebook server, a SysML API server, and a PostgreSQL database, all configured to work together seamlessly.

## Prerequisites

- [Visual Studio Code](https://code.visualstudio.com/)
- [Docker](https://www.docker.com/)
- [Remote - Containers](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) VSCode extension

## Getting Started

1. Clone this repository to your local machine.
2. Open the project folder in Visual Studio Code.
3. When prompted, click "Reopen in Container" or use the command palette (F1) and select "Remote-Containers: Reopen in Container".
4. Wait for the container to build and start. This may take a few minutes the first time.

## Project Structure

- `.devcontainer/`
  - `devcontainer.json`: Configuration for VSCode and the development container
  - `docker-compose.yml`: Defines the services (Jupyter, API, and Database)
  - `Dockerfile`: Builds the Jupyter notebook environment
  - `Dockerfile.api`: Builds the SysML API server environment
- `README.md`: This file

## Usage

### Jupyter Notebook

Once the container is running, you can access the Jupyter notebook by opening a new terminal in VSCode and running:

### SysML API

The SysML API is available at `http://localhost:9000` from your host machine.

### Database

The PostgreSQL database is running in its own container and is accessible to the other services. You can connect to it using the following credentials:

- Host: `postgresdbserver`
- Port: `5432`
- Username: `postgres`
- Password: `mysecretpassword`
- Database: `sysml2`

## Development

- Python files are automatically formatted and linted using Ruff when you save them.
- The Python interpreter is set to use the Conda environment created in the container.
- Additional VS Code settings and extensions are pre-configured for Python and Jupyter development.

## Customization

You can customize the environment by modifying the following files:

- `.devcontainer/devcontainer.json`: Add VS Code extensions or change settings
- `.devcontainer/docker-compose.yml`: Modify services or add new ones
- `.devcontainer/Dockerfile` and `.devcontainer/Dockerfile.api`: Change the base image or install additional packages

## Troubleshooting

If you encounter any issues:

1. Ensure Docker is running on your machine.
2. Try rebuilding the container: Command Palette (F1) > "Remote-Containers: Rebuild Container"
3. Check the "Remote-Containers" output panel in VS Code for error messages.

## Contributing

Feel free to open issues or submit pull requests if you have suggestions for improvements or encounter any problems.

## License

Both [SysMLv2 API Server](https://github.com/Systems-Modeling/SysML-v2-API-Services/blob/master/LICENSE) and [SysMLv2 Release](https://github.com/Systems-Modeling/SysML-v2-Release/blob/master/LICENSE) are licensed under the LGPL and this continues to be the case.

**This project does not make any changes to the existing licensing of the
referenced projects.**