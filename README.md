# Install-EB-CLI-Action
Install the Elastic Beanstalk CLI to the GitHub runner

# Usage
See [action.yml](action.yml)

**NOTE:** This Action presumes that you have AWS credentials appropriately configured in the GitHub environment.

Basic:
```yaml
steps:
- uses: aws-actions/configure-aws-credentials@v1  # AWS credentials are expected to be set up
- uses: sparkplug-app/install-eb-cli-action
- run: eb cli <my project>
```