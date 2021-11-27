# https://kubernetes.io/docs/tasks/access-application-cluster/port-forward-access-application-cluster/


kubectl port-forward mongo-75f59d57f4-4nd6q 28015:27017

kubectl port-forward pods/mongo-75f59d57f4-4nd6q 28015:27017

kubectl port-forward deployment/mongo 28015:27017

kubectl port-forward replicaset/mongo-75f59d57f4 28015:27017

kubectl port-forward service/myservice 28015:80