# SafePlaces Databases

## Overview

Two databases are required in order to store data for the services that comprise the SafePlaces backend. The two databases implement their own schemas and should be deployed independently of one another. Information on how to setup and configure these databases can be found [here](initial-setup.md).

### Motivation for Two Databases

The motivation for having two databases is to create separation between user data submitted via the PathCheck GPS mobile application and redacted GPS data created via SafePlaces. This separation of data ensures that any potentially sensitive data is not exposed through publicly accessible API endpoints.

### Public Database

The public database is utilized by the Backend service, Ingest Service, and SafePlaces Translation Service. The primary role of the public database is to store data uploaded by users of the PathCheck GPS mobile application.

### Private Database

The private database is utilized by the SafePlaces Backend service and Translation Service. The primary role of the private database is to store organization configuration data and data from contact tracing interviews conducted in SafePaths.
