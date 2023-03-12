# Role Based Access Contol on Kubernetes
---

# **Role** 
Avec les rôles, il est possible de définir des permissions    
Lié à un namespace, il est possible de définir quels sont les ressources de ce namespace   
à quoi on peut accéder et quelles actions pouvons nous y effectuer  
Les rôles sont limitées aux namespaces  
```
---
apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  name: rbac-role-role
rules:
  - apiGroups: [""] # "" Indique le Core API group
    resources: ["pods"]
    verbs: ["get", "watch", "list"] # Actions
```

# **RoleBinding**  
Permet d'assigner un role à un user ou groupe  
```
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: rbac-role-binding-role-binding
subjects:
  - kind: User | Group 
    name: jane | "devops-admins" # Sensible à la casse
    apiGroup: rbac.authorization.k8s.io
roleRef:
  kind: Role  # Role ou ClusterRole
  name: rbac-role-binding-role
  apiGroup: rbac.authorization.k8s.io
```
## RoleBinding pour ServiceAccount
```
apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: rbac-role-binding-role-binding
subjects:
  - kind: ServiceAccount
    name: default 
    namespace: kube-system
roleRef:
  kind: Role  # Role ou ClusterRole
  name: rbac-role-binding-role
  apiGroup: rbac.authorization.k8s.io
```

# **ClusterRole**  
Semblable aux "rôles" mais avec un scope "Cluster Wide" plutôt que namespace   
```
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRole
metadata:
  name: cluster-role-simple
rules:
  - apiGroups: [""]
    resources: ["secrets"]
    verbs: ["get", "watch", "list"]
```

# **ClusterRoleBinding**  
Permet d'assigner un ClusterRole à un user ou groupe  
```
apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: cluster-role-binding-clusterrolebinding-simple
subjects:
  - kind: Group
    name: manager 
    apiGroup: rbac.authorization.k8s.io
roleRef:
  kind: ClusterRole
  name: cluster-role-binding-clusterrole-simple
  apiGroup: rbac.authorization.k8s.io
```

**ServiceAccount**  
Les services account servent à représenter des applications nécessitant des accès au Cluster 
`kubectl create serviceaccount account1` 
Pareil que pour les **users ou groupe**, les **ServiceAccount(app)** peuvent être liés au **role ou ClusterRole** 
avec respectivement **RoleBinding ou ClusterRoleBinding** 

## Authors

- [@Ulrich NOUMSI](https://www.linkedin.com/in/ulrich-steve-noumsi/)

