Create a custom role with permissions to 

Deploy 
State full set 
Daemon Set 

Create a service account cicdtoken in a specific namespace bind the account with role and limited to the namespace app-team-1 



> kubectl get pod mypod -o yaml
> kubectl exec -it mypod -- sh 

>> curl https://kubernetes/api/v1 --insecure 

>> TOKEN=$(cat /run/secrets/kubernetes.io/serviceaccount/token)

>> curl -H "Authorization: Bearer $TOKEN" https://kubernetes/api/v1 --insecure 

# by default no access to default namespace 

curl -H "Authorization: Bearer $TOKEN" https://kubernetes/api/v1/namespaces/default/pods --insecure 



list roles 
kubectl api-resources --sort-by name -o wide

list verbs
kubectl api-resources --no-headers --sort-by name -o wide | sed 's/.*\[//g' | tr -d "]" | tr " " "\n" | sort | uniq



$ kubectl create role read-only --verb=list,get,watch \
  --resource=pods,deployments,services