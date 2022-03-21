# Install EB CLI
This GitHub Action install the Elastic Beanstalk CLI directly to the GitHub runner, for use in subsequent actions.  It persists the executable to the runner's PATH, so it can be used as you would expect in any other environment.

## Prerequisites
This Action presumes that you have AWS credentials appropriately configured in the GitHub environment.  Check out [this GitHub Action from AWS](https://github.com/aws-actions/configure-aws-credentials) for an example of how you might go about setting this up.

## Examples
Here's an example that installs the EB CLI in order to deploy an application's source bundle directly to an Elastic Beanstalk environment.

```yaml
steps:
- uses: actions/checkout@v2
- uses: aws-actions/configure-aws-credentials@v1
  with:
    aws-access-key-id: ${{ secrets.AWS_ACCESS_KEY_ID }}
    aws-secret-access-key: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
- uses: sparkplug-app/install-eb-cli-action
- run: eb init <ENVIRONMENT_NAME>
- run: eb deploy <APPLICATION_NAME>
```