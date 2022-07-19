## Creating a NodePort service

```
kubectl expose deployment web --target-port=8080 --type=NodePort
```

## Autoscaling a deployment

```
kubectl autoscale deployment web --max 4 --min 1 --cpu-percent 1
```

## Getting a list of Horizontal Pod Autoscalers

```
kubectl get hpa
```

## Deploying a node pool with three preemptible VM instances

```
gcloud container node-pools create "temp-pool-1" \
--cluster=$my_cluster --zone=$my_zone \
--num-nodes "2" --node-labels=temp=true --preemptible
```

## Add a taint to each node so that pods do not execute on preemptible instances

```
kubectl taint node -l temp=true nodetype=preemptible:NoExecute
```