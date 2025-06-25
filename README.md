# Kubernetes

kubectl apply -f /home/lukasz/Desktop/pod_nginx.yaml 

lukasz@minikube:~$ kubectl apply -f /home/lukasz/Desktop/pod_nginx.yaml
pod/nginx created

lukasz@minikube:~$ kubectl get pods
NAME    READY   STATUS             RESTARTS      AGE
nginx   0/1     CrashLoopBackOff   6 (84s ago)   4m20s

Kubectl exec
---------------
