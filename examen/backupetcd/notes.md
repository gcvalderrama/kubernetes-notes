
sudo apt install etcdctl 

ETCDCTL_API=3 etcdctl  -h

sudo ETCDCTL_API=3 etcdctl snapshot save snapthot.db \
--endpoints=https://127.0.0.1:2379 \
--cacert=/etc/kubernetes/pki/etcd/ca.crt \
--key=/etc/kubernetes/pki/etcd/server.key \
--cert=/etc/kubernetes/pki/etcd/server.crt


ps aux | grep etcd




sudo ETCDCTL_API=3 etcdctl --write-out=table snapshot status snapshot.db


ls /etc/kubernetes/pki/etcd/

sudo ETCDCTL_API=3 etcdctl snapshot save salida.txt