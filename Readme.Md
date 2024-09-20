Name:Nur Athirah Azhar

Q1:
Create a deployment named nginx in the qq2 namespace using the nginx image with 3 replicas.


Q2:
Create a new deployment name lab-deployment in the qq2 namespace. With one replica in the manifest then scale the deployment to 4 replicas.

Q3:
Create a deployment names nginx-deployment in the qq3 namespace. Perform a update to the deployment by setting the image to nginx:alpine.

Q4:

Create a new deployemnt called Python in programming namespace use the following image:

python:3.9.20-slim-bullseye

Make sure the cloud system can access it using port 9797

controlplane $ nano python-deployment.yaml
controlplane $ kubectl apply -f python-deployment.yaml
Error from server (BadRequest): error when creating "python-deployment.yaml": Deployment in version "v1" cannot be handled as a Deployment: strict decoding error: unknown field "spec.selector.matchLables"
controlplane $ nano python-deployment.yaml
controlplane $ nano python-deployment.yaml
controlplane $ kubectl apply -f python-deployment.yaml
Error from server (NotFound): error when creating "python-deployment.yaml": namespaces "programming" not found
controlplane $ kubectl create ns programming
namespace/programming created
controlplane $ kubectl apply -f python-deployment.yaml -n programming
deployment.apps/python created
controlplane $ 

Q:5
Create a pod named limit using the redis image in the qq3 namespace with the following resource limits and requests:

RequestsCPU: 0.5Memory: 500MiLimitsCPU: 1Memory: 1Gi

controlplane $ kubectl create namespace qq3
namespace/qq3 created
controlplane $ nano limit-pod.yaml
controlplane $ kubectl apply -f limit-pod.yaml -n qq3
Error from server (BadRequest): error when creating "limit-pod.yaml": Pod in version "v1" cannot be handled as a Pod: json: cannot unmarshal string into Go struct field PodSpec.spec.containers of type []v1.Container
controlplane $ nano limit-pod.yaml
controlplane $ kubectl apply -f limit-pod.yaml -n qq3
pod/limit created

Q6:
Create a Deployment named web in the ca1 namespace with an image of nginx:latest. Create a new Service named web-svc that sits in front of this deployment.  All changes should be performed in the ca1 namespace. 

controlplane $ kubectl create ns ca1
namespace/ca1 created
controlplane $ nano web-deployment.yaml
controlplane $ nano web-service.yaml
controlplane $ kubectl apply -f web-deployment.yaml -n ca1
deployment.apps/web created
controlplane $ kubectl apply -f web-service.yaml -n ca1
service/web-svc created
controlplane $ kubectl get all -n ca1
NAME                      READY   STATUS    RESTARTS   AGE
pod/web-d56774b7f-gttcw   1/1     Running   0          27s

NAME              TYPE        CLUSTER-IP      EXTERNAL-IP   PORT(S)   AGE
service/web-svc   ClusterIP   10.106.141.17   <none>        80/TCP    14s

NAME                  READY   UP-TO-DATE   AVAILABLE   AGE
deployment.apps/web   1/1     1            1           27s

NAME                            DESIRED   CURRENT   READY   AGE
replicaset.apps/web-d56774b7f   1         1         1       27s
controlplane $ 

Q7:

Execute the following requirements in the prod namespace. Create a new Deployment named app01 using the nginx:latest container image and have it listen on port 80. The deployment should consist of 2 replicas. Create a new Service named app01-svc and expose the newly created deployment using a NodePort. Confirm that you can access the nginx home (index) page using the NodePort service.

controlplane $ kubectl create ns prod
namespace/prod created
controlplane $ nano dep.yaml
controlplane $ nano svc.yaml
controlplane $ kubectl apply -f dep.yaml -n prod
deployment.apps/app01 created
controlplane $ kubectl apply -f svc.yaml -n prod
service/app01-svc created

Q8:
Create a new Deployment named cloud-app01 in the ca2 namespace consisting of 2 replicas. The deployment should use image nginx:1.23.3-alpine. Create a new Service resource named cloud-app-svc to expose the cloud-app01 deployment on port 80 in the same namespace. Finally use the following kubectl run command to spin up a utility pod which tests HTTP connectivity through the new service. Confirm that the following command returns an HTTP 200 response code:

kubectl run -n ca2 -i --tty --restart=Never --rm netutil --image cloudacademydevops/networkutils:v2 -- curl -I cloud-app-svc

controlplane $ nano dep.yaml
controlplane $ nano svc.yaml
controlplane $ kubectl apply -f dep.yaml -n ca2
deployment.apps/cloud-app01 created
controlplane $ kubectl apply -f svc.yaml -n ca2
The Service "cloud-app-svc" is invalid: spec.ports[0].nodePort: Forbidden: may not be used when `type` is 'ClusterIP'
controlplane $ nano svc.yaml
controlplane $ kubectl apply -f svc.yaml -n ca2
service/cloud-app-svc created
controlplane $ kubectl run -n ca2 -i --tty --restart=Never --rm netutil --image cloudacademydevops/networkutils:v2 -- curl -I cloud-app-svc
If you don't see a command prompt, try pressing enter.
curl: (7) Failed to connect to cloud-app-svc port 80: Connection refused
pod "netutil" deleted
pod ca2/netutil terminated (Error)
controlplane $ kubectl run -n ca2 -i --tty --restart=Never --rm netutil --image cloudacademydevops/networkutils:v2 --curl -I cloud-app-svc
error: unknown flag: --curl
See 'kubectl run --help' for usage.
controlplane $ kubectl run -n ca2 -i --tty --restart=Never --rm netutil --image cloudacademydevops/networkutils:v2 -- curl -l cloud-app-svc
If you don't see a command prompt, try pressing enter.
curl: (7) Failed to connect to cloud-app-svc port 80: Connection refused
pod "netutil" deleted
pod ca2/netutil terminated (Error)
controlplane $ nano svc.yaml
controlplane $ nano dep.yaml
controlplane $ kubectl run -n ca2 -i --tty --restart=Never --rm netutil --image cloudacademydevops/networkutils:v2 -- curl -l cloud-app-svc
If you don't see a command prompt, try pressing enter.
curl: (7) Failed to connect to cloud-app-svc port 80: Connection refused
pod "netutil" deleted
pod ca2/netutil terminated (Error)
controlplane $

Q9:
Create a deployment named class using httpd:alpine3.20
image configured with the following settings:

use the proper service type and service to expose it for ports 443 and 80

controlplane $ nano dep.yaml 
controlplane $ kubectl apply -f dep.yaml       
error: error parsing dep.yaml: error converting YAML to JSON: yaml: line 8: did not find expected key
controlplane $ nano dep.yaml 
controlplane $ kubectl apply -f dep.yaml 
deployment.apps/class created
controlplane $ 

Q10:
Create a deployment names busybox with an image of busybox:uclibc in the namespace busybox

Show the output and logs for the adminstrator to see

Q11:

Create a deployment names db in the database namespace which uses mysql:oraclelinux9. All teh enviromental variable must be set and the deployment myst be fully operational


Q12:
Deploy a pod named nginx using the nginx image in the qq3 namespace with Create a service related to this pod which is going to expose the pod with port 80 just within the Kubernetes

Q13:

Show the nodes associated with the current deployment of Kubernetes in your machine.

Q14:

Create a deployment names nginx-deployment in the qq3 namespace. Perform a rolling update to the deployment by setting the image to nginx:alpine.

Q15:
Create a new deployment name apache-deployment with an image of caleed httpd:latest

 in the qq3 namespace. Perform rolling update to the image httpd:bookworm and then a rollback of the deployment to restore the original image.


Q16:
Deploy  postgres by using Deployment with the following image:

https://hub.docker.com/_/postgres





Q17:

Then use elastio/pgadmin to create a database and change for the previous question

https://hub.docker.com/r/elestio/pgadmin



