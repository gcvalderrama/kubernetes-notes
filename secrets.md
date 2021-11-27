kubectl create secret generic secretstuff --from-literal=password=password

    volumeMounts:
        -mountPath: /secretstuff
         name: secret

volumes
-name: secret
 secret:
    secretName: secretstuff

