# client 

/etc/kubernetes/admin.conf 
~/.kube/config

kubectl config get-contexts

kubectl config view 

kubectl auth can-i --list --as johndoe 


# create namespace 
kubectl create ns mynamespace 

kubectl get ns 

# create pod 
command: ['sleep', '3600']

kubectl explain pod.spec
kubectl create -f 144.yaml
kubectl get pods 

kubectl delete pod $name
# reset bash
cp /etc/skel/.bashrc ~/.bashrc

kubectl completion -h
source <(kubectl completion bash)
# kubectl completion bash >> ~/.bashrc

# initi containers

> container 
name: busybox:1.28
command: ['sleep', '10000']

> init command 
command : ['sh', '-c', 'mkdir /data; touch /data/runfile.txt']


# configuring storage 

kubectl explain persistentvolume.spec

hostPath:
    path: /tmp

kubectl get pv 
kubectl get pvc

    volumeMounts:
    -mountPath: /var/
     name:mypd
volumes:
    -name: mypd
     persistentVolumeClaim:
        claimName: 


# running pod once

JOB or restart polidy

kubectl explain job.spec

spec:
 template:
    metadat: 
        name: ....

    containers:
    -   name: pi
        image: alpine
        restartPolicy: Never

# managing updates 


kubectl create deployment ex148 --image=nginx:1.14

kubectl --record deployment.app/ex148 set image deployment.v1.apps/ex148 nginx=nginx:latest

kubectl rollout history deployment ex148

kubectl rollout undo deployment ext148

# using labels 

kubectl get all --all-namespaces --selector k8s-app=kube-dns

# confgi maps

kubectl create configmap ext1410-cm --from-literal myuser=mypassword

kubectl get cm ext1410-cm -o yaml


env: 
    name: myuser
    valueFrom:
        configMapKeyRef:
            name: ex1410-cm 
            key: myuser 


kubectl logs ex1410-pod 

# running parallel pods 

daemon set 

vim :%s/text/replace/g

# mark node as unavailable

kubectl get nodes 

kubectl cordon #node
kubectl drain node  --force 

kubectl uncordon #node 

# using maintenance mode 

kubectl cordon $node

kubectl uncordon $node 

# backup etcd database 

etcd snapshot save 

sudo apt install etcdctl 

etcdctl --endpoints  snapshot save db

ETCDCTL_API=3 etcdctl -h

ETCDCTL_API=3 etcdctl snapshot 

ps aux | grep etcd

ETCDCTL_API=3 etcdctl --cacert=/etc/kubernetes/pki/etcd/ca.crt --cert /etc/kubernetes/pki/etcd/server --key /etc/.... --endpoints https://:2379 snapshot save /var/exam/etcbak

# using dns expose pod

kubectl expose busy33 --port=3333 

kubectl exec -it busy33 nslookup busy33


ssh root@worker1 systemctl stop firewalld

# auto start node in /etc/kubernetes/manifests

static pod 

ps aux | grep kubelet 
in /var/lib/kubelet/config.yaml 
search staticPodpath: # pods
cd /etc/kubernetes/manifests/

create file

systemctl restart kubelet

# finding the pod with the highest cpu load 


git clone https://github.com/kubernetes-incubator/metrics-server.git 

kubectl create -f metrics-server/deploy/1.8+/

args
  - --kubelet-insecure-tls
  - --kubelet-preferred-address-types= InternalIP,ExternalIP,Hostname

kubectl -n kube-system log metrics-...

kubectl top pods --all-namespaces

# network policies 

kind: NetworkPolicy 
apiVersion: networking.k8s.io/v1
metadata:
    name: only-allow-from-busybox-secure-ns
    namespace: default
spec:
    podSelector:
        matchlabels:
            app:web
    ingress:
    - from:
        - namespaceSelector:
            matchLabels:
                type: secure 
          podSelector:
            matchLabels:
                type: monitoring 


kubectl run newnginx --image=nginx
kubectl label pod newnginx app=web 

kubectl expose pod newnginx --port=80
kubectl get pods -n secure --show-labels

kubectl exec -n secure busybox2 -- wget --spider --timeout=1 newnginx.default.svc.local
error
kubectl exec -n secure busybox3 -- wget --spider --timeout=1 newnginx.default.svc.local



# create HA cluster

kubeadm init --control-plane-endpoint "192.168.4.100:8443" --upload-certs

copy output to text 

su - student 
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config  

sudo chown $(id -u): $(id -g) $HOME/.kube/config 
ls -l .kube/config 

apply cni pluging
kubectl apply -f 




            












command: []























