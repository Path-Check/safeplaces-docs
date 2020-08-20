# SafePlaces Services & Libraries

## [SafePlaces Backend Service](https://github.com/Path-Check/safeplaces-backend)

### Overview & Usage

The SafePlaces Backend Service is an internal service that is utilized by the SafePlaces Frontend to configure an organization and create, stage, and publish cases.

### Database Configuration Requirements

The SafePlaces Backend Service requires a database connection to the private database.

## [SafePlaces Ingest Service](https://github.com/Path-Check/safeplaces-backend-ingest/tree/master)

### Overview & Usage

The SafePlaces Ingest Service is a public facing standalone API. This service is utilized by the SafePaths Mobile Application to upload GPS data to.

### Database Configuration Requirements

The SafePlaces Ingest Service requires a single database connection to the public database.
SafePlaces Translation Service

## [SafePlaces Translation Service](https://github.com/Path-Check/safeplaces-backend-translation/tree/master)

### Overview & Usage

The SafePlaces Translation Service is a private standalone API that is utilized by the SafePlaces Frontend to create, delete, update, and query for GPS points associated with a case or set of cases.

GPS Points are collected by the SafePlaces mobile application and persisted across the public and private databases in discreet format. In discreet format, each GPS point consists of a latitude, longitude, a time, and implicitly represents a five minute window of time with the beginning of the five minute window relative to the time property. An example of three consecutive data points (consecutively five minutes apart from each other) in discreet format would look like the following:

```
[
  {
    "longitude": 14.91328448,
    "latitude": 41.24060321,
    "time": "2020-05-30T18:25:00.511Z"
  },
  {
    "longitude": 14.91328448,
    "latitude": 41.24060321,
    "time": "2020-05-30T18:30:00.511Z"
  },
  {
    "longitude": 14.91328448,
    "latitude": 41.24060321,
    "time": "2020-05-30T18:35:00.511Z"
  }  
]
```

The contact tracing tool in the SafePlaces Frontend represents points as a function of time spent in a single location. This necessitates the translation of GPS point data from discreet format (above) to duration format. The three points in the above discreet format example would become a single GPS point consisting of latitude, longitude, time (start time), and duration, like the following example, when translated to duration format:

```
{
  "discreetPointIDs": [21, 22, 23],
  "longitude": 14.91328448,
  "latitude": 41.24060321,
  "time": "2020-05-30T18:25:00.511Z",
  "duration": 15
}
```

### Database Configuration Requirements

The SafePlaces translation service requires a database connection to the public and private database.

## Libraries

### [SafePlaces Data Layer](https://github.com/Path-Check/safeplaces-data-layer)

#### Overview & Usage
The Safe Places Data layer contains migrations, seeds, and the general schema for working with both the public and private libs. Under the hood this utilizes the Knex library. So all services can access the standard Knex commands.
This library is used by the SafePlaces Backend, SafePlaces Ingest, and SafePlaces Translation service.

More information on functionality can be found in the repo's README.

### [SafePlaces Auth](https://github.com/Path-Check/safeplaces-auth)

#### Overview & Usage

The SafePlaces Auth library supports Auth0 asymmetric JWT and Symmetric JWT authentication strategies. This library is currently used by the SafePlaces Backend and SafePlaces Translation services.

More information on functionality can be found in the repo's README.

### [SafePlaces Server](https://github.com/Path-Check/safeplaces-backend-lib)

#### Overview & Usage

The SafePlaces Server library is a pre-built Express server used across all SafePlaces services.

More information on functionality can be found in the repo's README.
