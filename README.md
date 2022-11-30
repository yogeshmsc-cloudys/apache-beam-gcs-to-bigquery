# apache-beam-gcs-to-bigquery

# Load data from Google Cloud Storage bucket to Bigquery table with transformation.

## Pre-requisites:

## Copy test-data.json to Cloud Storage bucket
```bash
gsutil cp test-data.json gs://your-bucket-name
```

## Create Bigquery table
Note: Copy only the contents of the fields array into the file.
```bash
bq mk --location=EU --schema purchase_details.json --table your-project-id:your-dataset.purchase_details
```

## Install the dependencies
```bash
pip install -r requirements.txt
```

## Configure environment with Google Cloud defaults - Varies depends on the environment

## Windows:

```bash
gcloud auth application-default login

$env:GOOGLE_APPLICATION_CREDENTIALS="C:\<path>\gcloud\application_default_credentials.json"
$env:GOOGLE_CLOUD_PROJECT="your-gcp-project-id"

gcloud config set project "your-gcp-project-id"
```

## Run the program on Cloud Shell
```bash
python main.py
```