# Database Setup

## Overview

This README will walk you through the steps needed to setup the public and private database used by SafePlaces services.

## PostgreSQL Installation

SafePlaces uses [knexjs](http://knexjs.org/) configured with a connection to two PostgreSQL databases. If setting up SafePlaces locally, you'll need to have PostgreSQL installed on your development machine. If deploying SafePlaces to a hosted environment, you'll need to setup and configure a PostgreSQL instance for SafePlaces services to interface with.

## 1. Create SafePlaces Database User

You'll need to provision a new password protected user with the `SUPERUSER` role in order to run database migrations. This can be accomplished by running the following sample commands:

1. Create the user

```
psql=# CREATE USER safepaths_user PASSWORD 'password';
```

2. Grant new user `SUPERUSER` privilege

```
psql=# ALTER USER safepaths_user WITH SUPERUSER;
```

## 2. Create SafePlaces Private Database

You can create the SafePlaces private database by copying the following command into your terminal prompt (substituting the database name as needed):

```
createdb safeplaces_private
```

## 3. Create SafePlaces Public Database

You can create the SafePlaces public database by copying the following command into your terminal prompt (substituting the database name as needed):

```
createdb safeplaces_public
```

## 4. Install PostGIS

If not already, install the PostGIS PostgreSQL extension. Information on how to install the extension can be found [here](https://postgis.net/install/).
