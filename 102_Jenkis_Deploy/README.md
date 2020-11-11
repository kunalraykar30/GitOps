# Jenkins Deployment on Kubernetes with Persistent Volume

I wish to preserve preserve the contents of the JENKINS_HOME directory. So in case if new pod is spinned up the contents of Jenkins are preserved.
In order to get this done, PV and PVC are created - pv-jenkins.yaml and pvc-jenkins.yaml. Jenkins stores all of its important information within the JENKINS_HOME such as:

build server configuration.
build jobs.
build artifacts.
user accounts.
user installed plugins.

I have written differnt yaml files for differnt objects. However, all of these objects can be created in one go.
Below is the sequence in the which the objects should be created -

```
# kubectl create -f ns-jenkins.yaml
# kubectl create -f pv-jenkins.yaml
# kubectl create -f pvc-jenkins.yaml
# kubectl create -f deploy-jenkins.yaml
# kubectl create -f svc-jenkins.yaml 
```

Please: PV are not associated with namespace while PVC are associated with the namespace.
Hence, namespace has been mentioned in the pvc-jenkins.yaml. Do note that /var/jenkins_home is the actual home dir of the Jenkins.
Also, NodePort has been provided in the svc-jenkins but LoadBalancer can also be mentioned. 
