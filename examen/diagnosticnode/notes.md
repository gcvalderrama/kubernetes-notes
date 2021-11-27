ps aux | grep kubelet | grep yaml 

cd /etc/kubernetes/manifests/

vim kube manager scheduler

kubeadm config view 

systemd start the kubelet.service 

ps aux | grep kubelet 

kubelet starts Pods from /etc/kubernetes/manifests 

cd var/log/containers 


journalctl | grep kubelet


kubectl get all --selector app=mynginx

