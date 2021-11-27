kubectl expose deployment nginxsvc --port=80

kubectl describe svc nginxsvc

kubectl edit svc nginxsvc 

- port: 80
  protocol: TCP
  nodePort: 32000
  targetPort: 80

  type: NodePort # ClusterIP


kubectl run nginx-onport --image=nginx 
kubectl expose pod nginx-onport --port 80
kubectl edit svc nginx-onport 

- port: 80
  nodePort: 30080
  protocol: TCP
  targetPort: 80

type: NodePort 