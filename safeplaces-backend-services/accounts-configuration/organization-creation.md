
# Creation of Organization in SafePlaces

SafePlaces does not currently support the creation of organizations via the SafePlaces Frontend. As a result, it is recommend that you take the steps below to create an organization.

## Step to Creating an Organization

1. Run database seeds with the following command:

  `env $(cat .env) spdl seed:run --scope private --env development|staging|production`

2. Create a new user with the `admin` role and associate it with the organization created by the seeds (see: user_account_creation.md)

3. Login into SafePlaces Frontend with the newly created user's credentials - you'll be prompted to configure the newly created organization
