# Publishing Data via SafePlaces

## Overview

A case becomes eligible for publishing once a contact tracer has completed a their contact tracing interview and marked the case as "Staged for Publishing". At this point, a SafePlaces admin is able to select a collection of cases for publishing. When a publishing gets initiated the following steps occur:

1. The GPS points data associated with the published cases is randomized and then hashed
2. The hashed points data is then written to JSON files including metadata about the publishing
3. The JSON files are then pushed to the API endpoint that serves up the published points data for the PathCheck GPS application to process and create exposure alerts from

At this time, SafePlaces only supports pushing published data to a public Amazon Simple Storage Service bucket or a Google Cloud Storage bucket.

## Configuring Supported Cloud Storage Providers

Files can be published to either Google Cloud Storage (GCS) or AWS Simple Storage Service (S3). This preference is set via an environment variable in the SafePlaces Backend `.env` file.

```
PUBLISH_STORAGE_TYPE=(gcs|aws)
```

## Google Cloud Storage (GCS)

If using GCS, the following environment variables are required to be set in the SafePlaces Backend `.env` file:

```
GOOGLE_APPLICATION_CREDENTIALS='google_service_account.json'
GOOGLE_CLOUD_PROJECT=something
GCLOUD_STORAGE_BUCKET=somethingOrOther
```

## AWS Simple Storage Service (S3)

If using S3, the following environment variables are required to be set in the SafePlaces Backend `.env` file:

```
S3_BUCKET=bucket-name
S3_REGION=region-name
S3_ACCESS_KEY=something
S3_SECRET_KEY=something-secret
```
