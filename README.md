# Course_GKE_Beginner_To_Pro
1. configure kubectl in google cloud console
    gcloud container clusters get-credentials cluster-1 --zone=us-central1-c
2. kubectl port forwarding
    kubectl port-forward pod/pod_name local_port:container_port
3. Rollout the deployment to previous version
    kubectl rollout undo deployment/deployment_name
4. Check logs using selector
    kubectl logs --selector app=nginx
5. create service account
    gcloud iam service-accounts create SERVICE_ACCOUNT_NAME
    gcloud iam service-accounts create cloudsqlproxy
6. Grant role to service account
    gcloud projects add-iam-policy-binding PROJECT_ID --member "serviceAccount:SERVICE_ACCOUNT_EMAIL" --role "ROLE"
    gcloud projects add-iam-policy-binding playground-s-11-3f75ff3d  --member serviceAccount:cli-service-account-1@playground-s-11-3f75ff3d.iam.gserviceaccount.com --role roles/cloudsql.client
7. create service account key
    gcloud iam service-accounts keys create key.json --iam-account cli-service-account-1@playground-s-11-3f75ff3d.iam.gserviceaccount.com
8. create secret in k8s
    kubectl create secret generic cloudsql-instance-credentials --from-file=credentials.json=./key.json


====================================================================================================================================

1. deployment strategy
    1. rollout 
    A rollout deployment refers to the process of gradually updating an application version in a controlled manner, often using a rolling update strategy.

    2. canary
    A canary deployment is a strategy that involves releasing a new version of an application to a small subset of users or servers before rolling it out to the entire user base

    3. blue/green
    A blue-green deployment strategy involves maintaining two identical environments (blue and green) where only one is live at any given time.
