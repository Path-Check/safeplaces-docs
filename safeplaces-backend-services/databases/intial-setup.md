# Initial Setup of Public and Private Databases

Setup of the public and private databases will depend upon what context the databases are being deployed in. The general steps for setting up both databases can be found below. These steps will need to be done twice - once to create the public database and once to create the private database.

1. Create a new PostgreSQL database in your database provider of choice (i.e., Amazon Web Services, Google Cloud Suite, Microsoft Azure, self-hosted, etc.)

2. Provision a new user in the newly created database with a name and password

3. Alter newly created user's role to be `SUPERUSER`
