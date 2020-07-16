# Database Schemas and Migrations

Database schemas and migrations are maintained by the SafePlaces Data Layer library. The commands to run migrations should be executed on every deploy in order to keep the databases up-to-date. After initial setup of the public and private database they can be migrated by carrying out the following steps (NOTE: if deploying using docker these steps are already accounted for in the existing Dockerfile and dbsetup.sh script included in the SafePaths Backend repo):

1. If not already done, install the latest version of the `@pathcheck/data-layer` library globally by running the following:

  `npm install -g @pathcheck/data-layer`

2. If not already done, copy the `.env.template` file in the top-level of the SafePlaces Backend repository to a file named `.env` and make sure the following environment variables contain values that reflect your private and public database configurations:

  ```
  # Private Database Configuration Environment Variables
  DB_HOST (IP/URL of where database is hosted)
  DB_NAME (Name of database)
  DB_USER (Name of appropriately configured user)
  DB_PASS (Password for user)

  # Public Database Config Environment Variables (Ingest API Database)
  DB_HOST_PUB (IP/URL of where database is hosted)
  DB_NAME_PUB (Password for corresponding user)
  DB_USER_PUB (Name of appropriately configured user)
  DB_PASS_PUB (Password for user)
  ```

3. In the top-level directory of the SafePlaces backend application migrate the private database for the current environment using the following command:

  `env $(cat .env) spdl migrate:latest --scope private --env development|staging|production`

4. In the top-level directory of the SafePlaces backend application migrate the public database for the current environment using the following command:

  `env $(cat .env) spdl migrate:latest --scope public --env development|staging|production`
