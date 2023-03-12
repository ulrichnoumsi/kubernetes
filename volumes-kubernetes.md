
# Les Volumes sur Kubernetes
---
**Persistent Volume with nfs backend**
```
apiVersion: v1
kind: PersistentVolume
metadata:
  name: pv-name
spec:
  capacity:
    storage: 5Gi
  volumeMode: Filesystem
  accessModes:
    - ReadWriteOnce
  persistentVolumeReclaimPolicy: Recycle
  storageClassName: slow
  mountOptions:
    - hard
    - nfsvers=4.1
  nfs:
    path: /path/on/nfs/server
    server: nfs-server-ip-address
```
**Persistent Volume with Google cloud backend**
```
apiVersion: v1
kind: PersistentVolume
metadata:
  name: test-volume
  labels: 
    failure-domain.beta.kubernetes.io/zone: us-central1-a__us-central1-b
spec:
  capacity:
    storage: 400Gi
  accessModes:
    - ReadWriteOnce
  gcePersistentDisk:
    pdName: my-data-disk
    fsType: ext4
```
**Persistent Volume using Local volume**
```
apiVersion: v1
kind: PersistentVolume
metadata:
  name: example-pv
spec:
  capacity:
    storage: 100Gi
  volumeMode: Filesystem
  accessModes:
  - ReadWriteOnce
  persistentVolumeReclaimPolicy: Delete
  storageClassName: local-storage
  local: 
    path: /mnt/disk/ssd1
  nodeAffinity: 
    required: 
      nodeSelectorTerms:
      - matchExpressions:
        - key: kubernetes.io/hostname
          operator: In
          values: 
          - example-node
```

**PERSISTENT VOLUME CLAIM**
```
apiVersion: v1
kind: PersistentVolumeClaim
metadata:
  name: pvc-name
spec:
  storageClassName: [manual OR storage-class-name] 
  volumeMode: Filesystem
  accessModes:
    - ReadWriteOnce
  resources:
    requests:
      storage: 5Gi

```
```
#Pod using PVC
apiVersion: v1
kind: Pod
metadata:
  name: mypod
spec:
  containers:
    - name: myPodContainer
      image: nginx
      volumeMounts:
      - mountPath: "/var/www/html"
        name: my-volume
  volumes:
    - name: my-volume
      persistentVolumeClaim: 
        claimName: pvc-name
```

**STORAGE CLASS NAME**

```
apiVersion: storage.k8s.io/v1
kind: StorageClass
metadata:
  name: storage-class-name
provisioner: kubernetes.io/aws-ebs
parameters:
    type: io1
    iosPerGb: "10"
    fsType: ext4
```






## Authors

- [@Ulrich NOUMSI](https://www.linkedin.com/in/ulrich-steve-noumsi/)

