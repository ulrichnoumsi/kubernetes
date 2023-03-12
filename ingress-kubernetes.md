# Ingress on Kubernetes
---
**Ingress de base**
```
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: myapp-ingress
spec:
  rules:
  - host: myapp.com
    http: 
      paths:
      - backend:
          serviceName: myapp-internal-service
          servicePort: 80
```
```
**Ingress pour un seul Chemin**
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: myapp-ingress
  annotations:
    kubernetes.io/ingress.class: nginx
spec:
  rules:
  - host: xxx
    http:
        paths:
        - pathType: Prefix
          path: "/"
          backend:
            service:
              name: myapp-ingress service
              port:
                number: 8081
```
**Ingress avec Plusieurs chemin**
```
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: myapp-ingress
spec:
  rules:
  - host: myapp.com
    http: 
      paths:
      - path: /analytics
        backend:
          serviceName: myapp-internal-service
          servicePort: 80
      - path: /shopping
        backend:
          serviceName: myapp-internal-service
          servicePort: 80
```
**Ingress avec plusieurs sous domaine**
```
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: myapp-ingress
spec:
  rules:
  - host: analytics.myapp.com
    http: 
      paths:
        backend:
          serviceName: analytics-svc
          servicePort: 3000
  - host: shopping.myapp.com
    http: 
      paths:
        backend:
          serviceName: shopping-svc
          servicePort: 3000
```

**Configuration de l'ingress avec Https**
```
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: myapp-ingress
spec:
  tls:
  - hosts: 
    - myapp.com
    secretName: myapp-secret-tls
  rules:
  - host: myapp.com
    http: 
      paths:
      - path: /
        backend:
          serviceName: myapp-internal-service
          servicePort: 8080
```

## Authors

- [@Ulrich NOUMSI](https://www.linkedin.com/in/ulrich-steve-noumsi/)

