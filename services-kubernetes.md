## Les Différents services sur Kubernetes
---

**ClusterIP**
```
apiVersion: v1
kind: Service
metadata:
  name: clusterIP-svc
spec:
  selector:
    app: MyApp
  ports:
    - protocol: TCP
      port: 80
      targetPort: 9376
```
**LoadBalancer**
```
apiVersion: v1
kind: Service
metadata:
  name: LoadBalancer-svc
spec:
  selector:
    app: MyApp
  type: LoadBalancer
  ports:
    - protocol: TCP
      port: 80
      targetPort: 9376
      nodePort: [30000-32767]
```
**Headless Service**
```
apiVersion: v1
kind: Service
metadata:
  name: headless-svc
spec:
  clusterIP: None 
  selector:
    app: web
  ports:
    - protocol: TCP
      port: 80
      targetPort: 8080
```
**NodePort Service**
```
apiVersion: v1
kind: Service
metadata:
  name: nodePort-svc
spec:
  type: NodePort
  selector:
    app: MyApp
  ports:
    - port: 80
      targetPort: 80
      nodePort: [30000-32767]
```

## Authors

- [@Ulrich NOUMSI](https://www.linkedin.com/in/ulrich-steve-noumsi/)

