

**Name:** Muhammad Ikhmal Haziq bin Amar

---

### Q1:
Create a deployment named **nginx** in the **qq2** namespace using the `nginx` image with **3 replicas**.

---

### Q2:
Create a new deployment named **lab-deployment** in the **qq2** namespace. Initially, the manifest should have **one replica**, then scale the deployment to **4 replicas**.

---

### Q3:
Create a deployment named **nginx-deployment** in the **qq3** namespace. Update the deployment by setting the image to `nginx:alpine`.

---

### Q4:
Create a new deployment called **Python** in the **programming** namespace using the following image:

- `python:3.9.20-slim-bullseye`

Ensure the cloud system can access it using **port 9797**.

---

### Q5:
Create a pod named **limit** using the `redis` image in the **qq3** namespace with the following resource limits and requests:

- **Requests**: 
  - CPU: `0.5`
  - Memory: `500Mi`
- **Limits**:
  - CPU: `1`
  - Memory: `1Gi`

---

### Q6:
Create a deployment named **web** in the **ca1** namespace with the image `nginx:latest`. Create a new service named **web-svc** that sits in front of this deployment. All changes should be performed in the **ca1** namespace.

---

### Q7:
Execute the following requirements in the **prod** namespace:
- Create a new deployment named **app01** using the `nginx:latest` container image and have it listen on **port 80**.
- The deployment should consist of **2 replicas**.
- Create a new service named **app01-svc** and expose the deployment using a **NodePort**.
- Confirm access to the **nginx** home (index) page via the **NodePort** service.

---

### Q8:
Create a deployment named **cloud-app01** in the **ca2** namespace with **2 replicas** using the image `nginx:1.23.3-alpine`. Create a service named **cloud-app-svc** to expose the deployment on **port 80** in the same namespace. Use the following command to test HTTP connectivity:

```bash
kubectl run -n ca2 -i --tty --restart=Never --rm netutil --image cloudacademydevops/networkutils:v2 -- curl -I cloud-app-svc
```

Confirm that it returns an **HTTP 200** response code.

---

### Q9:
Create a deployment named **class** using the `httpd:alpine3.20` image with the following settings:
- Expose it using the proper service type for ports **443** and **80**.

---

### Q10:
Create a deployment named **busybox** using the `busybox:uclibc` image in the **busybox** namespace. Show the output and logs for the administrator to see.

---

### Q11:
Create a deployment named **db** in the **database** namespace using the `mysql:oraclelinux9` image. Set all the necessary environment variables and ensure the deployment is fully operational.

---

### Q12:
Deploy a pod named **nginx** using the `nginx` image in the **qq3** namespace. Create a service for this pod to expose it on **port 80** within Kubernetes.

---

### Q13:
Show the nodes associated with the current Kubernetes deployment in your machine.

---

### Q14:
Create a deployment named **nginx-deployment** in the **qq3** namespace. Perform a rolling update by setting the image to `nginx:alpine`.

---

### Q15:
Create a deployment named **apache-deployment** with the image `httpd:latest` in the **qq3** namespace. Perform a rolling update to the image `httpd:bookworm`, then roll back the deployment to the original image.

---

### Q16:
Deploy **Postgres** using a deployment with the following image:

- [Postgres Docker Hub](https://hub.docker.com/_/postgres)

---

### Q17:
Use **elestio/pgadmin** to create a database and modify it based on the previous question:

- [Elestio pgAdmin Docker Hub](https://hub.docker.com/r/elestio/pgadmin)
