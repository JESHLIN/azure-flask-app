Deploying a basic Flask application on Azure Web Apps.

Step 1: Prepare Your Flask Application
  -Create a directory for your Flask app.
  -Create a file named 'app.py'.
  -Create a 'requirements.txt' File
  -Create a 'Dockerfile' (This step is optional).
  -If you prefer using Docker, create a Dockerfile for containerizing your Flask app.

Step 2: Set Up Azure Web App
  -Go to the Azure Portal.
  -Navigate to App Services and click create web app.
  -Fill in the required fields.
  -Subscription and Resource Group.
  -Name: Your Web App name
  -Publish: Code (or Docker, if using a Dockerfile)
  -Runtime Stack: Choose Python 3.12
  -Region: Choose the closest region.
  
  Configure Continuous Deployment
  -Click Deployment Center.
  -Choose GitHub as the source.
  -Authorize Azure to access your GitHub account.
  -Select your repository and branch.
  -Click Review + create and then Create.

  Step 3: Set Up GitHub Actions for CI/CD
  -Create a GitHub Actions Workflow File.
  -In your GitHub repository, create a file named '.github/workflows/main_flask-web-apps.yml'
  
  Add Azure Publish Profile to GitHub Secrets:
  -In the Azure Portal, download the publish profile from your Web App (in the Deployment Center).
  -In GitHub, go to Settings > Secrets and variables > Actions.
  -Click New repository secret.
  -Name the secret 'MY_AZURE_PUBLISH_PROFILE'.
  -Paste the contents of the publish profile file into the Value field.
  -Click Add secret.

Step 4: Test and Monitor
  -Push Changes to GitHub:
  -Make a change to your Flask app or any file.
  -Commit and push the changes.

  Monitor the Deployment:
  -Go to your GitHub repository and click on the Actions tab.
  -Check the workflow run logs to ensure that the deployment completes successfully.
  -In the Azure Portal, monitor the Deployment Center.
  
  Verify the Deployment:
  -Visit your Azure Web App URL (It will be found in the Overview section of the Azure Portal).
  -You should see your Flask application running with the message "Hello, Azure Web Apps!".
