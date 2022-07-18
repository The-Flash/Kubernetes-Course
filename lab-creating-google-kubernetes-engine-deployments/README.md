## configuring access to cluster for kubectl commandline tool
```
gcloud container clusters get-credentials $my_cluster --zone $my_zone
```

## Scaling up/down pods
```
kubectl scale --replicas=3 deployment nginx-deployment
```

## Changing image of container in deployment
```
kubectl set image deployment.v1.apps/nginx-deployment nginx=nginx:1.9.1 --record
```

## View rollout status
```
kubectl rollout status deployment.v1.apps/nginx-deployment
```

## View rollout history
```
kubectl rollout history deployment nginx-deployment
```

## Trigger a deployment rollback
```
kubectl rollout undo deployments nginx-deployment
```