# starting cluster 
mkdir -p $HOME/.kube 
sudo cp -l /etc/kubernetes/admin.conf $HOME/.kube/config 
sudo chown $(id -u):$(id -g) $HOME/.kube/config 
kubectl cluster-info