# Kubernetes

kubectl apply -f /home/lukasz/Desktop/pod_nginx.yaml 

lukasz@minikube:~$ kubectl apply -f /home/lukasz/Desktop/pod_nginx.yaml
pod/nginx created

lukasz@minikube:~$ kubectl get pods
NAME    READY   STATUS             RESTARTS      AGE
nginx   0/1     CrashLoopBackOff   6 (84s ago)   4m20s

Kubectl exec       np. kubectl exec nginx -- ps aux
---------------
kubectl exec -ti 

ukasz@minikube:~/Desktop$ kubectl apply -f aplikacja.yaml 
pod/app created
lukasz@minikube:~/Desktop$ kubectl get pods
NAME   READY   STATUS    RESTARTS   AGE
app    2/2     Running   0          96s

lukasz@minikube:~/Desktop$ kubectl logs app
Defaulted container "ubuntu" out of: ubuntu, nginx

ukasz@minikube:~/Desktop$ kubectl get pods
NAME    READY   STATUS    RESTARTS   AGE
app     2/2     Running   0          5m49s
nginx   1/1     Running   0          6s

lukasz@minikube:~/Desktop$ kubectl logs nginx
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2025/06/25 20:28:50 [notice] 1#1: using the "epoll" event method
2025/06/25 20:28:50 [notice] 1#1: nginx/1.29.0
2025/06/25 20:28:50 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14+deb12u1) 
2025/06/25 20:28:50 [notice] 1#1: OS: Linux 6.8.0-60-generic
2025/06/25 20:28:50 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2025/06/25 20:28:50 [notice] 1#1: start worker processes
2025/06/25 20:28:50 [notice] 1#1: start worker process 29
2025/06/25 20:28:50 [notice] 1#1: start worker process 30
2025/06/25 20:28:50 [notice] 1#1: start worker process 31
2025/06/25 20:28:50 [notice] 1#1: start worker process 32

------------------------------------------------------------------------------------------------------------
ukasz@minikube:~/Desktop$ kubectl logs app nginx
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2025/06/25 20:23:31 [notice] 1#1: using the "epoll" event method
2025/06/25 20:23:31 [notice] 1#1: nginx/1.29.0
2025/06/25 20:23:31 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14+deb12u1) 
2025/06/25 20:23:31 [notice] 1#1: OS: Linux 6.8.0-60-generic
2025/06/25 20:23:31 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2025/06/25 20:23:31 [notice] 1#1: start worker processes
2025/06/25 20:23:31 [notice] 1#1: start worker process 29
2025/06/25 20:23:31 [notice] 1#1: start worker process 30
2025/06/25 20:23:31 [notice] 1#1: start worker process 31
2025/06/25 20:23:31 [notice] 1#1: start worker process 32

ukasz@minikube:~/Desktop$ kubectl logs app -c nginx
/docker-entrypoint.sh: /docker-entrypoint.d/ is not empty, will attempt to perform configuration
/docker-entrypoint.sh: Looking for shell scripts in /docker-entrypoint.d/
/docker-entrypoint.sh: Launching /docker-entrypoint.d/10-listen-on-ipv6-by-default.sh
10-listen-on-ipv6-by-default.sh: info: Getting the checksum of /etc/nginx/conf.d/default.conf
10-listen-on-ipv6-by-default.sh: info: Enabled listen on IPv6 in /etc/nginx/conf.d/default.conf
/docker-entrypoint.sh: Sourcing /docker-entrypoint.d/15-local-resolvers.envsh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/20-envsubst-on-templates.sh
/docker-entrypoint.sh: Launching /docker-entrypoint.d/30-tune-worker-processes.sh
/docker-entrypoint.sh: Configuration complete; ready for start up
2025/06/25 20:23:31 [notice] 1#1: using the "epoll" event method
2025/06/25 20:23:31 [notice] 1#1: nginx/1.29.0
2025/06/25 20:23:31 [notice] 1#1: built by gcc 12.2.0 (Debian 12.2.0-14+deb12u1) 
2025/06/25 20:23:31 [notice] 1#1: OS: Linux 6.8.0-60-generic
2025/06/25 20:23:31 [notice] 1#1: getrlimit(RLIMIT_NOFILE): 1048576:1048576
2025/06/25 20:23:31 [notice] 1#1: start worker processes
2025/06/25 20:23:31 [notice] 1#1: start worker process 29
2025/06/25 20:23:31 [notice] 1#1: start worker process 30
2025/06/25 20:23:31 [notice] 1#1: start worker process 31
2025/06/25 20:23:31 [notice] 1#1: start worker process 32
----------------------------------------------------------------------------------------------------------

Dwa kontenery w Pod
-----------------------

lukasz@minikube:~/Desktop$ kubectl describe pod app | grep "IP"
IP:               10.244.0.3
IPs:
  IP:  10.244.0.3
lukasz@minikube:~/Desktop$ 

lukasz@minikube:~/Desktop$ kubectl exec -it app -- bash

lukasz@minikube:~/Desktop$ kubectl exec -it app -- bash
Defaulted container "ubuntu" out of: ubuntu, nginx
root@app:/# ps -aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.0   4544  1280 ?        Ss   20:23   0:00 sleep inf
root           7  0.1  0.0  18520  3200 pts/0    Ss   20:39   0:00 bash
root          17  0.0  0.0  34416  2688 pts/0    R+   20:39   0:00 ps -aux
root@app:/# 

ukasz@minikube:~/Desktop$ kubectl exec -c nginx -it app -- bash
root@app:/# 

10.244.0.3



