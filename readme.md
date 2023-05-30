# Project SonarQube Integration

This project contains code that integrates with SonarQube, a platform for continuous code quality inspection. The integration allows importing GitHub projects into SonarQube and setting up SonarQube workflows for automated code analysis.

## Prerequisites

Before running this code, make sure you have the following prerequisites:

- Python 3.x installed
- `config.yaml` file with the following configuration:
  - `github_token`: GitHub personal access token with necessary permissions
  - `sonarqube_token`: SonarQube token for authentication
  - `sonarqube_host`: URL of the SonarQube server
  - `organization`: GitHub organization name
  - `alm_setting`: ALM (Application Lifecycle Management) setting for SonarQube integration
  - `runs_on`: Target platform for SonarQube workflows (e.g., `ubuntu-latest`, `windows-latest`, `macos-latest`)

## Installation

1. Clone this repository to your local machine:

   ```shell
   git clone <repository_url>
   ```

2. Install the required dependencies by running the following command:

   ```shell
   pip install -r requirements.txt
   ```

## Usage

1. Open the `config.yaml` file and provide the required configuration values.

2. Run the following command to execute the code:

   ```shell
   python main.py
   ```

   The script will perform the following steps for each repository in the specified GitHub organization:

   - Clone the repository locally.
   - Import the GitHub project into SonarQube.
   - Create a `sonar-project.properties` file for the project.
   - Create a SonarQube workflow file (`sonarqube.yml`) in the repository's `.github/workflows` directory.
   - Commit and push the changes to the repository.

3. After running the script, the GitHub repositories will be integrated with SonarQube, and the SonarQube workflows will be set up for continuous code analysis.

## Note

- Make sure the provided GitHub personal access token has the necessary permissions to access and modify repositories.
- Ensure that the SonarQube server is accessible and the provided SonarQube token has sufficient privileges.
- The code assumes the presence of a `sonar-project.properties` file in each repository. If the file doesn't exist, it will be created during the integration process.
- The code uses the GitHub API and the `git` Python library to clone repositories and perform Git operations. Make sure these dependencies are installed.

For any issues or questions, please contact the project maintainers.