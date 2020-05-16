# React, Cognito, Amplify and no CLI!

Starting out with React and Cognito I didn't find a lot of useful examples on how to connect these.  There are hand crafted libraries, a deprecated AWS JS library and Amplify (to name a few I am sure).  Originally I shunned amplify because I wanted to use CDK on the front end and it appeared to be it's own thing.

After digging a bit I found some issues related to documenting the `./aws-exports` file ([one](https://github.com/aws-amplify/docs/issues/766), [two](https://github.com/aws-amplify/amplify-js/issues/1753)) and the [Amplify docs](https://docs.amplify.aws/lib/auth/start/q/platform/js#re-use-existing-authentication-resource) that document how to stitch these together without using the Amplify CLI.  Note that not all the *required* fields seem to be required... ¯\\\_(ツ)\_/¯ .

References:
* Original react sample on the AWS docs: https://docs.amplify.aws/lib/auth/social/q/platform/js#refreshing-jwt-tokens
* More details on configuring Amplify without ./aws-exports: https://docs.amplify.aws/lib/auth/start/q/platform/js#re-use-existing-authentication-resource
* Configuring Cognito for oauth signup and getting it to work with React (custom util + redux):
  * Part 1 (configuring cognito): https://itnext.io/aws-cognito-example-using-react-ui-and-node-js-rest-apis-part-1-cognito-setup-5597acb02db4
  * Part 2 (React APP): https://itnext.io/aws-cognito-example-using-react-ui-and-node-js-rest-apis-part-2-react-ui-app-with-redux-6cc22610affe
  * Part 2 (Authenticating API calls): https://itnext.io/aws-cognito-example-using-react-ui-and-node-js-rest-apis-part-3-jwt-secured-rest-apis-e56d336ce306
  * Github for the sample used above: https://github.com/arronharden/cognito-demo-ui

### Using This example

This example is self contained so use it as you would any React app, just rename `amplify.config.json.dist` to `amplify.config.json` and fill in the appropriate values.  So long as your ccognito pool is configured correctly you should be able to sign in/out.
