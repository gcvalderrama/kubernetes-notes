
kubectl get ns trouble -o json > trouble.json

kubectl replace --raw "/api/v1/namespaces/trouble/finalize/" -f trouble.json

