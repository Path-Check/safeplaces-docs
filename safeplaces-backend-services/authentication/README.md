# SafePlaces Authentication

## Overview

The [SafePlaces Auth Library](https://github.com/Path-Check/safeplaces-auth) contains all functionality related to user authentication. Under the hood, the auth library interfaces with [Auth0](https://auth0.com/). Auth0 provides authentication as a service and offers the ability to integrate with a [number of identity providers](https://auth0.com/docs/connections/identity-providers-enterprise). At this time, SafePlaces does not support any authentication strategies beyond what Auth0 allows.

## Getting Started with Auth0

You'll need to create an Auth0 account, setup a new connection, setup an API, and create a a user within Auth0 to get started using SafePlaces. Information on the previously mentioned can be found in [Auth1 Getting Started Guide](https://auth0.com/docs/getting-started).

## Configuring Your SafePlaces Instance

The below environment variables will need to be set and present in the `.env` file of your [SafePlaces Backend](https://github.com/Path-Check/safeplaces-backend) and [SafePlaces Translation Service](https://github.com/Path-Check/safeplaces-backend-translation) instances in order for your users to successfully login.

```
AUTH_LOGOUT_REDIRECT_URL # URL for Auth0 to redirect to after a user logs out
AUTH0_BASE_URL # Tenant url from Auth0 (https://auth0.com/docs/getting-started/the-basics)
AUTH0_CLIENT_ID # Found in your Auth0 application's settings page
AUTH0_CLIENT_SECRET # Found in your Auth0 application's settings page
AUTH0_API_AUDIENCE # name of API you've setup in Auth0
AUTH0_CLAIM_NAMESPACE # See https://auth0.com/docs/tokens/guides/create-namespaced-custom-claims
AUTH0_REALM # name of connection in Auth0
```
