#  validate permissions 
kubectl auth can-i create deployment --as linda 
kubectl auth can-i create deployment --namespace secret


kubectl cluster-info 
kubectl config view 

# help 
kubectl cluster-info -h

# options for accesing the api

kubectl api-resources  # api groups within the apis 
curl http://localhost:8001/apis

kubectl api-versions
kubectl explain csistoragecapacities

# enable auto completion

install bash-completion 

kubectl completion bash >> ~/.bashrc
kubectl completion bash > /etc/bash_completion.d/kubectl 

# conenct without certs

kubectl proxy --port=8001 &

curl http://localhost:8001/api/v1/namespaces/default/pods

# intereact with etcd 

etcdctl 






