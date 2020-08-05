# Setting Up SafePlaces

## Overview

This README will walk you through the steps needed to setup all SafePlaces services for local development or to deploy SafePlaces without using Docker.

## General Setup Steps

### Installing NVM

Instructions on how to install NVM can be found [here](https://github.com/nvm-sh/nvm#installing-and-updating).

### Installing & Configuring Node

After installing NVM, install node using nvm and configure your environment to use the correct version with the following commands:

```
nvm install 14.0.0
nvm use 14.0.0
```

## Installing SafePlaces Data Layer

Install the SafePlaces data-layer library using the following command:

```
npm install -g @pathcheck/data-layer --unsafe-perm
```

### Migrate & Seed Private Database

You can migrate and seed the private database using the following commands (specifying one of the correct environments in commands below):

```
env $(cat .env) spdl migrate:latest --scope private --env development|staging|production

env $(cat .env) spdl seed:run --scope private --env development|staging|production
```

### Migrate and Seed Public Database

You can migrate and seed the public database using the following commands (specifying one of the correct environments in commands below):

```
env $(cat .env) spdl migrate:latest --scope public --env development|staging|production

env $(cat .env) spdl seed:run --scope public --env development|staging|production
```

## Setting Up SafePlaces Backend Service

You should be able to successfully setup the SafePlaces Backend service by executing the below steps. Some steps will only need to be done once across all services and can be skipped if already taken care of (ex., setting up databases).

1. If not already in place, create both the public and private databases (see [guide on initial database setup](../databases/initial-setup.md))

2. Copy the .env.template file in the top-level of the repo and populate variables with values relevant to your deployment (see [here](../environment-variables/safeplaces-backend-service.md) for an overview of required environment variables)

3. If not already, install NVM (see above for details)

4. If not already, install Node (see above for details)

5. In the top-level directory of the repo install all dependencies by running `npm install`

6. If you haven't already, migrate and seed both the public and private databases (see above for details)

7. Start application by running `npm start`

## Setting Up SafePlaces Translation Service

You should be able to successfully setup the SafePlaces Translation service by executing the below steps. Some steps will only need to be done once across all services and can be skipped if already taken care of (ex., setting up databases).

1. If not already in place, create both the public and private databases (see [guide on initial database setup](../databases/initial-setup.md))

2. Copy the .env.template file in the top-level of the repo and populate variables with values relevant to your deployment (see [here](../environment-variables/safeplaces-translation-service.md) for an overview of required environment variables)

3. If not already, install NVM (see above for details)

4. If not already, install Node (see above for details)

5. In the top-level directory of the repo install all dependencies by running `npm install`

6. If you haven't already, migrate and seed both the public and private databases (see above for details)

7. Start application by running `npm start`


## Setting Up SafePlaces Ingest Service

You should be able to successfully setup the SafePlaces Ingest service by executing the below steps. Some steps will only need to be done once across all services and can be skipped if already taken care of (ex., setting up databases).

1. If not already in place, create the public database (see [guide on initial database setup](../databases/initial-setup.md))

2. Copy the .env.template file in the top-level of the repo and populate variables with values relevant to your deployment (see [here](../environment-variables/safeplaces-ingest-service.md) for an overview of required environment variables)

3. If not already, install NVM (see above for details)

4. If not already, install Node (see above for details)

5. In the top-level directory of the repo install all dependencies by running `npm install`

6. If you haven't already, migrate and seed the public database (see above for details)

7. Start application by running `npm start`
