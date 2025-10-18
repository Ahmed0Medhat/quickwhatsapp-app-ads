# QuickWhatsApp App Ads

This repository contains the `app-ads.txt` file for the QuickWhatsApp application.

## GitHub Actions Deployment

The repository includes a GitHub Actions workflow that automatically deploys the `app-ads.txt` file to the root domain at `https://ahmed0medhat.github.io/app-ads.txt`.

### Setup Instructions

To enable automatic deployment, you need to create a Personal Access Token (PAT) and add it as a repository secret:

1. **Create a Personal Access Token:**
   - Go to GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
   - Click "Generate new token (classic)"
   - Give it a name like "Deploy app-ads.txt"
   - Select the `repo` scope (full control of private repositories)
   - Click "Generate token" and copy the token

2. **Add the token as a repository secret:**
   - Go to this repository's Settings → Secrets and variables → Actions
   - Click "New repository secret"
   - Name: `PAT_TOKEN`
   - Value: Paste the token you created
   - Click "Add secret"

3. **Trigger the workflow:**
   - The workflow will automatically run when you push changes to `app-ads.txt` on the `main` branch
   - You can also manually trigger it from the Actions tab

### How it works

When the workflow runs, it:
1. Checks out this repository
2. Checks out the `Ahmed0Medhat.github.io` repository
3. Copies the `app-ads.txt` file from this repo to the root repository
4. Commits and pushes the changes

This ensures that the app-ads.txt file is accessible at `https://ahmed0medhat.github.io/app-ads.txt` instead of the project-specific URL.
