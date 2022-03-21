# Install-EB-CLI-Action
This GitHub Action install the Elastic Beanstalk CLI directly to the GitHub runner, for use in subsequent actions.  It persists the executable to the runner's PATH, so it can be used as you would expect in any other environment.

# Examples

**NOTE:** This Action presumes that you have AWS credentials appropriately configured in the GitHub environment.

Basic:
```yaml
steps:
- uses: aws-actions/configure-aws-credentials@v1  # AWS credentials are expected to be set up
- uses: sparkplug-app/install-eb-cli-action
- run: eb cli <my project>
```