# Creation of Users In SafePlaces

SafePlaces does not currently support the creation of users via the SafePlaces Frontend. As a result, users will need to be created directly in the private database.

## Steps to Creating a New User in SafePlaces

1. Create a new user in Auth0 with a role value of one of the following:

- `super_admin` - this role allows the user to create and manage other users' permissions within SafePlaces
- `contact_tracer` - this role allows the user to create/update cases, modify GPS point data, and stage cases for publishing
- `admin` - this role allows the user to carry out all action of a `contact_tracer`, configure their organization's settings, and publish case data

2. In Auth0, open the user details of the newly created user and locate the user's ID (begins with the characters `auth0|`) and make note of it

3. Connect to the private database

4. Locate the `id` (primary key) of the organization you'll be creating a user for by running the following command and make note of it.

5. Create a new user in the database using the following command (substituting the appropriate values for  `organization_id`, `username`, and  `idm_id`):

  `INSERT INTO users (id, organization_id, username, idm_id) VALUES (uuid_generate_v4(), organization_id, username, idm_id);`
