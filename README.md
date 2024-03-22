# Kubernetes

## Kubernetes on Docker Desktop
1. kubectl config get-contexts
2. kubectl config get-clusters
3. kubectl config use-context docker-desktop
4. kubectl get nodes

## Dashboard UI
1. kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml
2. kubectl proxy

## User Creation for Dashboard
1. Service Account
2. kubectl apply -f dashboard-adminuser.yaml
3. Cluster Role Binding
4. kubectl apply -f cluster-role-binding.yaml
5. Get Token
6. kubectl -n kubernetes-dashboard create token admin-user
7. Long Lived Token
8. kubectl get secret admin-user -n kubernetes-dashboard -o jsonpath={".data.token"} | base64 -d

## ConfigServer YML
1. kubectl get deployments
2. kubectl get services
3. kubectl get replicasets
4. kubectl get pods
5. kubectl apply -f configserver.yml
