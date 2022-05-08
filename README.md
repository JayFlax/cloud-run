# Cloud Run Practice app 
##### Practice deploying a monolithic app containerized with cloud build/docker and deployed on Cloud Run
##### Service URL: https://monolith-wfmdhop44q-uw.a.run.app



## ACTIONS

1. Create project on GCP or use current project  
2. In terminal set project  
`gcloud config set project <project id>`
3. Make a new directory for your files   
	`mkdir cloudrun`  
	`cd cloudrun`
4. Clone git repo  
	`git clone <repo>`
5. Change into correct directory  
`cd monolith-to-microservices`  (check files in editor and edit before running script)
6. Run startup script  
`./setup.sh`
7. Change to correct directory for build  
`cd monolith`  (to test run `npm start`)

8. Enable cloud build  
	`gcloud services enable cloudbuild.googleapis.com`
9. Start the build process  
	`gcloud builds submit --tag gcr.io/${GOOGLE_CLOUD_PROJECT}/monolith:1.0.0 .`  
### Deploy container to cloud run    
1. Enable cloud run services  
	`gcloud services enable run.googleapis.com`
2. Run to deploy  
	`gcloud run deploy --image=gcr.io/${GOOGLE_CLOUD_PROJECT}/monolith:1.0.0 --platform managed --max-instances=1`

