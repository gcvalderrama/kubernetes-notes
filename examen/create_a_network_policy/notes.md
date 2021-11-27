kubectl expose pod nwp-nginx --port=80

kubectl exec -it  nwp-busybox -- wget --spider --timeout=1  nwp-nginx

kubectl get pods  --show-labels 


kubectl label pod nwp-busybox access=true


apply to all namespace 

apiVersion: networking.k8s.io/v1
kind: NetworkPolicy
metadata:
  namespace: default
  name: deny-from-other-namespaces
spec:
  podSelector:
    matchLabels:      
  ingress:
  - from:
    - podSelector: {}