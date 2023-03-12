
# Installation de Kubernetes avec Minikube

Dans cette présentation il sera question de présenter l'installation d'un Cluster Kubernetes tout en un (All in One en anglais), pour pouvoir réaliser nos travaux d'Orchestrations.


## Procédure
### Préréquis
- Avoir un outils de virtualisation (VMWare, VirtualBox)
- Disposer d'une image de système d'exploitation Unix (Ubuntu - Debian - CentOS - RedHat)
- Disposer d'une Connexion Internet pour l'installation des différents paquets

### Installation
- **Installation du binaire kubectl avec curl**
```
curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl
```
- **Rendre le Binaire executable**
`chmod +x ./kubectl`

- **Déplacer le binaire dans le repertoire d'executable** 
`sudo mv ./kubectl /usr/local/bin/kubectl`

- **Tester la version Kubectl installé** 
`kubectl version --client`

- **Installation de Docker** \
 **Ubuntu - Debian :** `sudo apt-get update -y &&  sudo apt-get install -y docker.io` \
 **CentOS - RedHat :** `sudo yum update && sudo yum install -y docker.io`

- **Tester la version de Docker installée**
`sudo docker version`

- **Installation de Minikube**  <br>
```
curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64 \
&& chmod +x minikube \
&& sudo mv minikube /usr/local/bin/
```
- **Tester la version de minikube installé** 
`minikube version ` 

- **Démarrer minikube**
```
sudo -i
minikube start --driver=none
```

- **Installation de conntrack** 
Si erreur **Sorry, Kubernetes v1.18.0 requires conntrack to be installed in root's path** 
Executer `apt install conntrack` 

- **Tester l'etat de minikube**  
`minikube status`

## Authors

- [@Ulrich NOUMSI](https://github.com/MrUSN/)


## Liens Utils

[Documentation](https://kubernetes.io/fr/docs/setup/learning-environment/minikube/) \
[Ubuntu](https://ubuntu.com/download/) \
[Debian](https://www.debian.org/CD/http-ftp/) \
[CentOS](https://www.centos.org/download/)

