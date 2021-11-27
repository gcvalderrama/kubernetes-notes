kubectl taint nodes worker example-key=value:NoSchedule 

# kubectl taint nodes worker example-key=:NoSchedule- 

kubectl taint nodes worker example-key=value:NoSchedule 

kubectl create deployment nginx-taint --image=nginx 


apiVersion: v1
kind: Pod
metadata:
  name: nginx-toleration
  labels: 
    env: test
spec:
  containers:
  - name: nginx-toleration
    image: nginx
    imagePullPolicy: IfNotPresent
  tolerations:
  - key: "example-key"
    operator: "Exists"
    effect: "NoSchedule"
