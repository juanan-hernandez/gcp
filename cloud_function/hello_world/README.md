# DEPLOY TO GCP

## Previous steps.
### GUI
First of all, if needed, visit [enabling the service account](https://cloud.google.com/build/docs/securing-builds/configure-access-for-cloud-build-service-account)and make sure 

As well as [Cloud Functions API](https://console.cloud.google.com/apis/library/cloudfunctions.googleapis.com) and [Cloud Resource Manager API](https://console.cloud.google.com/apis/library/cloudresourcemanager.googleapis.com)

### CONSOLE
```bash
gcloud services enable cloudfunctions.googleapis.com
gcloud services enable cloudresourcemanager.googleapis.com
```

```bash
PROJECT_ID=halogen-oxide-362913
REGION=europe-west1
FUNCTION_NAME=hello_world
FUNCTION_RUNTIME=python310
gcloud builds submit --project=$PROJECT_ID --region=$REGION --substitutions=_FUNCTION_NAME=$FUNCTION_NAME,_REGION=$REGION,_FUNCTION_RUNTIME=$FUNCTION_RUNTIME .
```