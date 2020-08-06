# SafePlaces Backend Service Environment Variables

Below are a list of the environment variables required for the SafePlaces Backend service to function correctly. The variables and their values should be present in a file named `.env` located in the top-level directory of the repo. An example of the `.env` file can be found [here](https://github.com/Path-Check/safeplaces-backend/blob/master/.env.template).

## Environment Variables

### Database Environment Variables

Below are environment variables that need to be set in order for the SafePlaces backend service to interact with the public and private databases.

- DB_HOST - IP/URL of where private database is hosted
- DB_NAME - name of private database
- DB_USER - name of user database user
- DB_PASS - password for database user

- DB_HOST_PUB - IP/URL of where public database is hosted
- DB_USER_PUB - name of public database
- DB_NAME_PUB - name of user database user
- DB_PASS_PUB - password for database user

### Cloud Storage Environment Variables

Below are environment variables that need to be set in order to push published data to a cloud storage provider. Currently the SafePlaces Backend service supports pushing data to either AWS S3 or Google Cloud Storage.

- PUBLISH_STORAGE_TYPE - indicates the configured cloud storage provide (should be `gcs` for Google Cloud Storage or `aws` for Amazon S3)

- GCLOUD_STORAGE_BUCKET - name of bucket to upload published location data to (only needs to be set if PUBLISH_STORAGE_TYPE equals `gcs`)
- GCLOUD_STORAGE_PATH - folder of GCloud bucket to store published location data in (only needs to be set if PUBLISH_STORAGE_TYPE equals `gcs`)
- GOOGLE_SECRET - path to file containing Google secret (only needs to be set if PUBLISH_STORAGE_TYPE equals `gcs`)

- S3_BUCKET - name of S3 bucket to publish location data to (only needs to be set if PUBLISH_STORAGE_TYPE equals `aws`)
- S3_ACCESS_KEY - S3 access key (only needs to be set if PUBLISH_STORAGE_TYPE equals `aws`)
- S3_SECRET_KEY - S3 secret key (only needs to be set if PUBLISH_STORAGE_TYPE equals `aws`)

### Authentication Related Environment Variables

Below are environment variables that must be set in order to properly configure a connection to Auth0 to handle authentication and user management.

- AUTH_LOGOUT_REDIRECT_URL - URL for Auth0 to redirect to after a user logs out
- AUTH0_BASE_URL - tenant url from Auth0 (https://auth0.com/docs/getting-started/the-basics)
- AUTH0_REALM - name of connection in Auth0
- AUTH0_CLAIM_NAMESPACE - see https://auth0.com/docs/tokens/guides/create-namespaced-custom-claims

- AUTH0_API_AUDIENCE - name of Auth0 user management audience in Auth0
- AUTH0_CLIENT_ID - found in your Auth0 authorization application's settings page
- AUTH0_CLIENT_SECRET - found in your Auth0 authorization application's settings page

- AUTH0_MANAGEMENT_API_AUDIENCE - name of Auth0 user management audience in Auth0
- AUTH0_MANAGEMENT_CLIENT_SECRET - found in your Auth0 user management application's settings page
- AUTH0_MANAGEMENT_CLIENT_ID - found in your Auth0 user management application's settings page

- JWT_SECRET -  used to sign JWTs and should be at least 64 characters, and generated using a [secure source of randomness](https://cheatsheetseries.owasp.org/cheatsheets/Cryptographic_Storage_Cheat_Sheet.html#secure-random-number-generation)

### Miscellaneous Environment Variables

- NODE_ENV - indicates the environment the application is running in should be set to development, staging, or production depending on the context the application is running in

- BYPASS_SAME_SITE - sets the `SameSite` cookie attribute for authorization cookie returned by `/login`. Should be `false` for local development and `true` in all deployed environments.

- DOMAIN - sets the `Domain` cookie attribute for authorization cookie returned by `/login` should be set to the domain or subdomain all services are running under

- EXPRESSPORT - the port that the express server is running on

- DISPLAY_ERROR_MESSAGE - will return error messages from the API if set to `true` (should be set to `false` in production environments)
