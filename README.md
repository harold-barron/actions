
# Reusable GitHub Actions

This repository contains reusable GitHub Actions workflows designed to streamline the CI/CD process for Node.js applications. The workflows are designed to be flexible and can be included in other repositories as required.

## Workflows

### Build Workflows

1. **Build Node.js Static Webapp**
   - **File:** `.github/workflows/buildNodeJs_StaticWebapp.yaml`
   - **Description:** This workflow sets up a Node.js environment, installs dependencies, builds the project, optionally copies a `web.config` file, and uploads the build artifacts.
   - **Inputs:**
     - `package-path` (string, required)
     - `hasWebConfig` (boolean, optional, default: true)

2. **Build Node.js Project**
   - **File:** `.github/workflows/build_Node.yaml`
   - **Description:** This workflow sets up a Node.js environment, installs dependencies, builds the project if applicable, and uploads the build artifacts.
   - **Inputs:**
     - `package-path` (string, required)

### Deployment Workflows

1. **Deploy Node.js to Azure Static Web Apps**
   - **File:** `.github/workflows/deploy_Node_Azure_static.yaml`
   - **Description:** This workflow deploys the Node.js application to Azure Static Web Apps.
   - **Steps:**
     - Downloads build artifacts.
     - Logs in to Azure.
     - Deploys to Azure Static Web Apps.

2. **Deploy Node.js to Azure Web Apps**
   - **File:** `.github/workflows/deploy_Node_Azure.yaml`
   - **Description:** This workflow deploys the Node.js application to Azure Web Apps.
   - **Steps:**
     - Downloads build artifacts.
     - Logs in to Azure.
     - Deploys to Azure Web Apps.

3. **Deploy Node.js to Azure Static Web Apps (V2)**
   - **File:** `.github/workflows/deploy_Node_Azure_static_V2.yaml`
   - **Description:** This workflow deploys the Node.js application to Azure Static Web Apps using a token fetched from Azure.
   - **Steps:**
     - Downloads build artifacts.
     - Logs in to Azure.
     - Fetches the deployment token.
     - Deploys to Azure Static Web Apps.

## Usage

To use these workflows in your own repository, you can include them using the `workflow_call` event in your workflow files. Ensure that you have the necessary secrets and inputs configured in your repository settings.

## Contributing

If you would like to contribute to this repository, please fork the repository and create a pull request with your changes. Ensure that your changes are well-documented and include relevant test cases.

## License

This repository is licensed under the MIT License.

