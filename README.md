# GitOps Way
EKS+Jenkins+Sonarqube+Nexus+ArgoCD+Prometheus

While running the EKS makre sure the Access_key and Secret_key is updated in the code. 
Best pratice is to use the AWS_CLI and configure the credentils so the Credentails are not hard coded. 
Variables can be also be seperated instead of hard coding the values.

cd 102_Jenkins_Deploy

```
kubectl create -f ns-jenkins.yaml 
kubectl create -f deploy-jenkins.yaml
kubectl create -f svc-jenkins.yaml 

curl NODE_IP:32000
```
NodePort service is accessible on port 30000 across the cluster nodes. 


ArgoCD Deployment -

Run below command on the EKS. 

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml




