# GitOps
EKS+Jenkins+ArgoCD+Prometheus


cd 102_Jenkins_Deploy

kubectl create -f ns-jenkins.yaml 
kubectl create -f deploy-jenkins.yaml
kubectl create -f svc-jenkins.yaml 

curl NODE_IP:30000

NodePort service is accessible on port 30000 across the cluster nodes. 


ArgoCD Deployment -

Run below command on the EKS. 

kubectl create namespace argocd
kubectl apply -n argocd -f https://raw.githubusercontent.com/argoproj/argo-cd/stable/manifests/install.yaml




