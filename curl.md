kubectl proxy --port=8001 &

curl http://localhost:8001/api/v1/namespaces/default/pods 


curl -XDELETE http://localhost:8001/api/v1/namespaces/default/pods/busybox




