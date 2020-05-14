# DevOps Repo

## Useful tools

- The GCloud CLI ([here](https://cloud.google.com/sdk/docs)).

## Files

This repository manages the following files.

### `dispatch.yaml`

`dispatch.yaml` maps URLs to App Engine services ([documentation](https://cloud.google.com/appengine/docs/standard/python/how-requests-are-routed?_ga=2.191426927.-457884559.1588541219#routing_with_a_dispatch_file)).
To modify the mapping one needs to re-deploy the file (see command below).

## Common commands

- Set GCloud CLI to project : `gcloud config set project PROJECT-ID`

- Authenticate : `gcloud auth login`

- Reauthenticate : `gcloud auth revoke` and then `gcloud auth login`

- Deploy dispatch file (:warning: Ensure you set the CLI to the appropriate project !!): `gcloud app deploy dispatch.yaml`

