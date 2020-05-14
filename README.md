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


## How Tos

### Deploy a new App Engine Service from a new repo

1. Create repo on GitHub and push code.

2. Create `cloudbuild.yaml` file with the deploy command inside (see other repos for examples).

3. On Google Cloud Build, connect the GitHub repo and create a trigger

    a. When connecting the repo you might need to allow GC Build to access Github
    
    b. When creating the trigger, you'll need to specify the Branch.
    
4. If all worked well, run the trigger, and the service should deploy.

Optional steps to map the App Engine Service to a URL.

1. Add the URL in the AppEngine Settings -> Custom domains tab. 
You'll need to update the DNS records for the domain (either through Google Domains or gandi.net).

2. Update `dispatch.yaml` **carefully** and redeploy the dispatch file.