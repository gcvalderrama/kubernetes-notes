

kubectl create deployment ex148 --image=nginx:1.14

kubectl get pods 

kubectl --record deployment.apps/ex148 set image deployment.v1.apps/ex148 nginx=nginx:latest

kubectl rollout history deployment ex184

kubectl rollout undo deployment ex148