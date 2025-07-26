## In order to integrate Openshift with Okta with Oauth authentication follow this repository.

Prerequisite.

1. Ensure you have an application created on the Okta.
2. Openshift 4 SNO/CRC/Cluster running.
3. Openshift should able to reach Okta.

### Steps:

1. If you do not have Okta account and application, first create a trial account at [Okta](https://developer.okta.com/)
2. Create an application by following below steps.
3. Create App Inegartion by cliking on
4. Choose the Type as OIDC and Web application
5. Specify the Redirect URL of Openshift. It should be like below. Okta as last is the authentication source which you will be creating.
```bash
 https://your-cluster's-oauth-url/oauth/callback/okta
```
6. Now copy the Client ID and Secret for the Client ID and save the secret safely at a place.
7. Also copy the OKTA URL from the URL bar it should look like - https://dev-12345678-admin.okta.com/
8. Now Create a user by going ot the Directory > People > Add Person
9. Provide a username and email ID, Also choose Password as `set by admin` and set the password.
10. Now Open OCP cluster console.
11. Go to Administer >> Cluster Settings >> Configuration >> Oauth
12. At Bottom of page click on  Add >> OpenID connect
13.  Enter following details which we copied from the Okta console and then submit.
     Client ID
     Client Secret
     Issuer URL
14. For few minutes so that oauth pods can restart.
15. Now try to login with user which we created in Okta.
