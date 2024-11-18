# Course_GKE_Beginner_To_Pro
1. configure kubectl in google cloud console
    gcloud container clusters get-credentials cluster-1 --zone=us-central1-c
2. kubectl port forwarding
    kubectl port-forward pod/pod_name local_port:container_port
3. Rollout the deployment to previous version
    kubectl rollout undo deployment/deployment_name
4. Check logs using selector
    kubectl logs --selector app=nginx