# InstaWP WordPress Testing Automation
This custom action automates your WordPress testing. Integrate it with your InstaWP account and get going within minutes.

# Pre-req

- Register an account at [instawp.com](https://instawp.com)
- Create a site and upload your plugin/theme (download a zip from github and upload)
- Save the site as Template, give a unique slug
- Go to Deployment, enter the details of your WordPress plugin/theme repo. 
- Go back to Templates, connect the git repo to the template. 
- Paste this Yaml file into your repo as shown below.

# Yaml File

Paste this code in your `.github/workflows/instawp.yml` file

```
name: InstaWP WordPress Testing

on:
  pull_request:
    types: [opened]

jobs:
  create-wp-for-testing:
    runs-on: ubuntu-latest
    steps:
      - uses: instawp/wordpress-testing-automation@latest
        with:
          GITHUB_TOKEN: ${{secrets.GITHUB_TOKEN}}
          INSTAWP_TOKEN: ${{secrets.INSTAWP_TOKEN}}
          INSTAWP_TEMPLATE_SLUG: gutenademonew
          REPO_ID: 123
```

- INSTAWP_TOKEN can be obtained from your "API Tokens" screen inside the InstaWP interface. 
- INSTAWP_TEMPLATE_SLUG is shown on the "Templates" screen. 
- REPO_ID is shown in the "Deployment" screen.