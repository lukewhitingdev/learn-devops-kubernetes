# How to use
1. Run `kubectl apply -f deploy-app.yaml` to deploy the replicated nginx cluster
2. Run `kubectl apply -f deploy-services.yaml` to deploy the `NodePort` service to route traffic into the cluster
3. Run `kubectl port-forward service/app-cluster-service 80:80` to let you locally send traffic to the service and therefore the cluster 
4. Goto `http://localhost` in a browser and observe the glorious nginx default page

## To see logs for the pods you can run
`kubectl logs deployment/nginx-deployment --all-pods -f` to get real-time logs for all pods in the app deployment

# To remove
1. Run `kubectl delete -f deploy-app.yaml`
2. Run `kubectl delete -f deploy-services.yaml`