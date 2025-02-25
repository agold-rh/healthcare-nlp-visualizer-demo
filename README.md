# Healthcare NLP Visualizer Demo

The demo application is a Node.js and React.js system to visualize the 
Google Cloud [Healthcare Natural Language API](https://cloud.google.com/healthcare/docs/how-tos/nlp).
You can upload your own sample medical text to visualize the output such as medical dictionaries,
entity extraction and relationships, context assessment and more. We have also provided sample
texts for a a medical record, research paper and lab form. 

![screencast](screencast-short.gif)

## Prerequisites 

1. A GCP Project with billing and the Healthcare NLP API enabled.
1. Complete the Healthcare NLP [How-to Guide](https://cloud.google.com/healthcare/docs/how-tos/nlp).
    - Note: For the purposes of this demo, grant the new service account "Viewer", not "Owner".
1. Familiarity with Google Cloud Functions and Vue.js.

## Set Up Instructions

### Important

This demo will create a cloud function that is executable by ANYONE on the Internet. Be sure to 
delete it when your demonstration is complete.

### Backend

The HTTP Cloud Function can be found in the `/analyzeDocument` directory. Please note, this code is NOT
meant for production use.

1. ```grep``` the `/analyzeDocument` directory for the string `REPLACE`.
    - You will need to replace these placeholders with real values.
1. Download the service account key for your project.
1. Deploy the Cloud Function, you can follow the instructions [here](https://cloud.google.com/functions/docs/deploying).
    - See the sample invocation in `util/deploy_cf.sh`
1. Copy the endpoint for your Cloud Function.

### Frontend

The Vue.js app is found in the `/app` directory.

1. ```grep``` the `/app` directory for the string `REPLACE`.
    - You will need to replace these placeholders with real values.
1. ```cd app/```
1. Paste your Cloud Function endpoint in to the placeholder in index.html. 
1. Start a local server of your choice and open the application in your browser.
    - See the sample server in `util/server.py`.
