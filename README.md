# Extreme Startup

For this exercise we will use an automated build pipeline to deploy a simple web application. 
We will use GitHub Actions and Railway, which are easy to set up.

## Set Up a Build Pipeline

### 1. Fork our web app on GitHub, clone it and get it running locally

- Fork this repo into your own GitHub account.
- Clone your fork locally and import the code into an IDE.
- It’s a Java / Gradle project.

### 2. Push a change to trigger GitHub Actions

- The repository contains a .github directory that configures a GitHub Actions build pipeline.
- The file .github/workflows/build.yml configures the build and deploy pipeline.

- If you push a change to the Java code you should see the build pass, but the deploy stage will probably fail, as we need to set up a few more things.

- If you aren’t familiar with build pipelines or GitHub Actions you can check the documentation online here: https://docs.github.com/en/actions / https://docs.github.com/en/actions/quickstart

### 3. Setting up deployment to the cloud
- Create an account on Railway at railway.app (you’ll get a confirmation email etc).
- Create an empty project on Railway.
- Choose a unique name (e.g. we chose nameless-forest-60668)

### 4. Setting up automatic deployment to Railway with GitHub Actions

- Get your Railway API Token and add it to GitHub as a secret variable for your build pipeline. You can get it by navigating to Account Settings > Tokens. Provide a name in `New Token` > and click `Create`.
- Add this token on your GitHub fork by navigating to Settings > Secrets and Variables > Actions. Press `New repository secret` and provide a name and paste the generated Token by Railway.

### 5. Pushing changes through the pipeline
Make a change to your application (e.g. change some HTML in IndexPage). Commit, push and check it is deployed (e.g. at https://nameless-forest-60668.herokuapp.com/).

Now make a change to QueryProcessor (and its corresponding unit test) to make the app respond to a new query.
When the tests pass, commit, push, and deploy again.
Try intentionally breaking the build to make sure that only successful builds are deployed.
