
# ReplicaSet Demo

This guide demonstrates how to create and manage a Kubernetes ReplicaSet using a YAML file.

---

## 📝 Steps to Run

1. **Create the YAML file**

   Open a text editor and paste the YAML content:
   ```bash
   vi replicaset.yml

2. **Apply the YAML using kubectl**
   ```bash
   kubectl apply -f replicaset.yml
3. **Check the ReplicaSet**
   ```bash
   kubectl get rs
4. Check the Pods created by the ReplicaSet
   ```bash
   kubectl get pods
5. View logs from one of the Pods First, get the Pod name
   ```bash
   kubectl get pods
6. Use the Pod name to view logs
    ```bash
    kubectl logs <pod-name>
  Example:
    ```bash
    kubectl logs my-replica-jssvs


Output :

```bash
kubectl apply -f replicaset-demo.yml 
replicaset.apps/my-replica created


 kubectl get rs
NAME         DESIRED   CURRENT   READY   AGE
my-replica   3         3         3       17s


    kubectl get pods
NAME               READY   STATUS    RESTARTS   AGE
my-replica-jssvs   1/1     Running   0          2m45s
my-replica-rtxw6   1/1     Running   0          2m45s
my-replica-tx5zm   1/1     Running   0          2m45s

kubectl logs my-replica-rtxw6
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2025/04/16 19:04:51 [notice] 1#1: using the "epoll" event method
2025/04/16 19:04:51 [notice] 1#1: nginx/1.27.5
2025/04/16 19:04:51 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14) 
2025/04/16 19:04:51 [notice] 1#1: OS: Linux 5.4.0-1106-gcp
2025/04/16 19:04:51 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2025/04/16 19:04:51 [notice] 1#1: start worker processes
2025/04/16 19:04:51 [notice] 1#1: start worker process 81
2025/04/16 19:04:51 [notice] 1#1: start worker process 82
2025/04/16 19:04:51 [notice] 1#1: start worker process 83
2025/04/16 19:04:51 [notice] 1#1: start worker process 84
2025/04/16 19:04:51 [notice] 1#1: start worker process 85

