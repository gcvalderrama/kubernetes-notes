# depends on metrics server 
kubectl top pods --all-namespaces 

# store logs in
/api/v1/namespaces/default/pods/mypod/log 

> kubectl logs $mypod

# understanding pods 
kubectl create deployment error-busy --image=busybox 
kubectl describe pod $name


# 
systemd kubelet.service
ps aux | grep kubelet # to see the kubelet config


kubelet starts pods from /etc/kubernetes/manifests

kube-apiserver
etcd
kube-controller-manager
kube-scheduler 

journalctl | grep kubelet 
cd /var/log/containers 


kubectl get pods --show-labels

kubectl get all --selector app=nginx
kubectl describe pod 



