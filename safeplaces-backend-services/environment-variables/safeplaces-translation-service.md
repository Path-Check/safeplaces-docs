# SafePlaces Ingest Service Environment Variables

Below are a list of the environment variables required for the SafePlaces Translation service to function correctly. The variables and their values should be present in a file named `.env` located in the top-level directory of the repo. An example of the `.env` file can be found [here](https://github.com/Path-Check/safeplaces-backend-translation/blob/master/.env.template).

## Environment Variables

### Database Environment Variables

- DB_HOST - IP/URL of where private database is hosted
- DB_NAME - name of private database
- DB_USER - name of user database user
- DB_PASS - password for database user

- DB_HOST_PUB - IP/URL of where public database is hosted
- DB_USER_PUB - name of public database
- DB_NAME_PUB - name of user database user
- DB_PASS_PUB - password for database user

### Authentication Related Environment Variables

Below are environment variables that must be set in order to properly configure a connection to Auth0 to handle authentication.

- AUTH_LOGOUT_REDIRECT_URL - URL for Auth0 to redirect to after a user logs out
- AUTH0_BASE_URL - tenant url from Auth0 (https://auth0.com/docs/getting-started/the-basics)
- AUTH0_REALM - name of connection in Auth0
- AUTH0_CLAIM_NAMESPACE - see https://auth0.com/docs/tokens/guides/create-namespaced-custom-claims

- AUTH0_API_AUDIENCE - name of Auth0 user management audience in Auth0
- AUTH0_CLIENT_ID - found in your Auth0 authorization application's settings page
- AUTH0_CLIENT_SECRET - found in your Auth0 authorization application's settings page


### Miscellaneous Environment Variables

- NODE_ENV - indicates the environment the application is running in should be set to development, staging, or production depending on the context the application is running in

- EXPRESSPORT - the port that the express server is running on
