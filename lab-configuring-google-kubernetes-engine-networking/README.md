## Inspecting a cluster

```
gcloud container clusters describe private-cluster --region us-central1-a
```

## Creating a cluster and enabling network policy

```
gcloud container clusters create $my_cluster --num-nodes 3 --enable-ip-alias --zone $my_zone --enable-network-policy
```

## Configuring access to cluster for kubectl command

```
gcloud container clusters get-credentials $my_cluster --zone $my_zone
```

## Running a simple web server application with label app=hello

```
kubectl run hello-web --labels app=hello \
  --image=gcr.io/google-samples/hello-app:1.0 --port 8080 --expose
```

## Viewing network policies

```
kubectl get networkpolicy
```

## Running a temporary pod

```
kubectl run test-1 --labels app=foo --image=alpine --restart=Never --rm --stdin --tty
```