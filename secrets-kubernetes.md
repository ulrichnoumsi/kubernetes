## Les secrets sur Kubernetes

**Exemple de configuration de Base**
```
apiVersion: v1
kind: Secret
metadata:
  name: secret-sa-sample
  annotations:
    kubernetes.io/service-account.name: "sa-name"
type: kubernetes.io/service-account-token
data:
  # You can include additional key value pairs as you do with Opaque Secrets
  extra: YmFyCg==
```
**Exemple pour Ingress pour la confuguration des TLS**
```
apiVersion: v1
kind: Secret
metadata:
    name: myapp-secret-tls
    namespace: default
date:
    tls.crt: base64 encoded cert
    tls.key: base64 encoded key
type: kubernetes.io/tls
```

## Authors

- [@Ulrich NOUMSI](https://www.linkedin.com/in/ulrich-steve-noumsi/)

