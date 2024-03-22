# Kubernetes

## Kubernetes on Docker Desktop
1. kubectl config get-contexts
2. kubectl config get-clusters
3. kubectl config use-context docker-desktop
4. kubectl get nodes

## Dashboard UI
1. kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.7.0/aio/deploy/recommended.yaml
2. kubectl proxy
3. http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/#/login

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
5. kubectl get pvc
6. kubectl apply -f configserver.yml

## Config Map
1. kubectl apply -f configmap.yml

## Helm Charts
1. brew install helm
2. helm repo add bitnami https://charts.bitnami.com/bitnami
3. helm env
4. helm ls
5. helm create scaler-project
6. helm dependencies build
7. helm template .
8. helm install <name> <path>
9. helm upgrade <name> <path>
10. helm history <name>
11. helm rollback <name> <revision>
12. helm uninstall <name>
13. Delete pvc claims // Bug in Helm Uninstall
