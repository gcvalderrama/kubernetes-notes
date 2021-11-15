kubectl create deployment --image=nginx newnginx
kubectl get all 

kubectl create deployment --dry-run  --image=nginx  -o yaml demo 

kubectl scale deployment demo --replicas=3


kubectl get deployments --show-labels 

kubectl label deployments.apps demo state=demo 

kubectl get deployments.apps --selector state=demo 

kubectl get all --selector app=demo 

kubectl explain deployment.spec.strategy 

kubectl rollout history deployment 
kubectl edit deployments.app nginx 

kubectl rollout history deployment deploymentname

kubectl expose deployment nginx --port=80 --name=myservice 

kubectl get daemonset -n kube-system

kubectl exec -it demo -- /bin/bash 

kubectl get pv demo-pv

kubectl explain pv.spec
kubectl explain pv.spec.storageClassName



kubectl create deployment nginxsvc --image=nginx 
kubectl scale deployment nginxsvc --replicas=3
kubectl expose deployment nginxsvc --port=80

kubectl get svc 
kubectl describe nginxsvc 
kubectl get pods --show-labels 
kubectl get endpoints 
kubectl edit 

kubectl create deploy ghost --image=ghost --record

kubectl get deployments ghost -o yaml


kubectl set image deployment/ghost ghost=ghost:09 --all

kubectl rollout history deployment/ghost deployments

kubectl get pods

kubectl rollout undo deployment/ghost ; kubectl get pods


kubectl create deploy busybox --image=busybox --command sleep 3600

kubectl exec -ti <busybox_pod> -- /bin/sh 


kubectl debug buggypod --image debian --attach

kubectl krew install sniff nginx-123456-abcd -c webcont

kubectl expose deployment/nginx --port=80 --type=NodePort

export key=$(grep client-key-data ~/.kube/config | cut -d " " -f 6)

kubectl config set-context anna-context --cluster=kubernetes --namespace=staff --user=anna


kubectl --context=anna-context get pods 

kubectl describe role staff


# --to-revision=2 


# create service account 

kubectl 
# in a pod 
curl -H "Authorization: Bearer $TOKEN" https://kubernetes/api/v11/namespaces/default/pods --insecure

TOKEN=$(cat /run/secrets/kubernetest.io/serviceaccount/token)


sudo useradd bob
sudo usermod -aG wheel bob

mkdir .kube
cp /etc/kubernetes/admin.conf .kube/config

sudo chown bob:bob .kube/config

# cni

cd /etc/cni 

kubectl exec podname cat /etc/resolv.conf

# verify dns is running
kubectl get pods --namespace=kube-system -l k8s-app=kube-dns

# check logs 

for p in $(kubectl get pods --namespace=kube-system -l k8s-app=kube-dns -o name); do kubectl logs --namespace=kube-system $p; done


# verify dns service is up
kubectl get svc -n kube-system
# verify endpoints 
kubectl get ep kube-dns -n kube-system

# disable all firewalling on all nodes 
iptables -F && iptables -t nat-F && iptables -t mangle -F && iptables  -X

# remove dns and recreate
kubectl delete pod -n kube-system -l k8s-app=kube-dns # calico is better than wave

# check dns 

kubectl exec -it busybox2 -- nslookup kubernetes
kubectl exec -it busybox2 -- cat /etc/resolv.conf


# test connectivity  
kubectl exec -it nwp-busybox -n nwp-namespace -- wget --spider --timeout=1 nwp-nginx.default.svc.cluster.local

# reenebale completion
source <  (kubectl completion bash)

# export port 
kubectl expose pod nginx-onport --port 80

kubectl edit svc nginx-onport 

https://github.com/sandervanvugt/cka

kubeadm token create 


kubectl cordon $node 
kubectl drain 

# config kubelet 
cat /var/lib/kubelet/conf.yaml


# remove node

kubectl cordon # kubectl uncordon
kubectl drain --delete-local-data --force --ignore-daemonsets
kubectl delete node 

kubeadm reset
rm $HOME/.kube/config

# status nodes

systemctl status kubelet
ps aux | grep kubelet | grep yaml

cd /etc/kubernetes /manifests  / kube-controller.yaml














kubetc

Concluciones

Los alumnos mostro un buen desempenio en el curso , realizando preguntas y buscando expandir 
su conocimiento a nuevos escenarios.

Los laboratorios fueron apropiados para que las personas mejoren su conocimiento en Azure. 

Los casos particulares presentados por los alumnos fueron absueltos en clases.


Recomendaciones

Profundizar en los conocimientos especificos por area, como pueden ser la adminsitracion de sistemas, desarrollo de software y analisis de datos en la plataforma Azure con el fin de maximizar el retorno de inversion en Cloud