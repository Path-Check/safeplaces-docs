# SafePlaces Ingest Service Environment Variables

Below are a list of the environment variables required for the SafePlaces Ingest service to function correctly. The variables and their values should be present in a file named `.env` located in the top-level directory of the repo. An example of the `.env` file can be found [here](https://github.com/Path-Check/safeplaces-backend-ingest/blob/dev/.env.template).

## Environment Variables

### Database Environment Variables
- DB_HOST_PUB - IP/URL of where public database is hosted
- DB_USER_PUB - name of public database
- DB_NAME_PUB - name of user database user
- DB_PASS_PUB - password for database user

### Miscellaneous Environment Variables

- NODE_ENV - indicates the environment the application is running in should be set to development, staging, or production depending on the context the application is running in

- EXPRESSPORT - the port that the express server is running on
