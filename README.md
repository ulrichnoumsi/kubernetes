![Logo de Kubernetes](/images/kubernetes.png.png)
# Présentation de Kubernetes

Kubernetes est une plate-forme open-source extensible et portable pour la gestion de charges de travail (workloads) et de services conteneurisés. Elle favorise à la fois l'écriture de configuration déclarative (declarative configuration) et l'automatisation. C'est un large écosystème en rapide expansion. Les services, le support et les outils Kubernetes sont largement disponibles.


## Architecture de Kubernetes
Kubernetes fonctionne sur la base d'un état défini et d'un état réel. Les objets Kubernetes représentent l'état d'un cluster. Ils indiquent à Kubernetes à quoi vous voulez que la charge de travail ressemble.

![Architecture Kubernetes](/images/kubernetes-constructs-concepts-architecture.jpg)

## Quelques éléments à connaitre
- **Noeuds** 
Machines qui exécutent les tâches qui leur sont assignées par le plan de contrôle.
- **Pod**
Un ou plusieurs conteneurs déployés sur un seul nœud. Le pod est l'objet Kubernetes le plus petit et le plus simple.
- **Kubectl** 
Interface en ligne de commande dans laquelle vous pouvez gérer votre cluster Kubernetes. En savoir plus sur les commandes de base kubectl et Helm pour débutants.
- **Service**
Méthode qui permet d'exposer une application exécutée sur un ensemble de pods en tant que service réseau. Le service dissocie la définition des tâches des pods.
- **Kubelet**
Minuscule application située au sein de chaque nœud qui communique avec le plan de contrôle. Le kubelet s'assure que les conteneurs sont exécutés dans un pod.
- **Plan de contrôle**
Le plan de contrôle. Il contient les composants Kubernetes qui contrôlent le cluster, ainsi que des données sur l'état et la configuration du cluster. Ces principaux composants de Kubernetes s'assurent que suffisamment de conteneurs peuvent fonctionner avec les ressources nécessaires. 

Le plan de contrôle est en contact permanent avec vos machines de calcul. Vous avez configuré votre cluster pour qu'il fonctionne d'une certaine manière. Le plan de contrôle s'assure que votre configuration est respectée.

- **kube-apiserver**
Vous avez besoin d'interagir avec votre cluster Kubernetes ? C'est à cela que sert l'API. L'API de Kubernetes est la partie frontale du plan de contrôle. Elle prend en charge les demandes internes et externes. Le serveur d'API détermine si une demande est valide ou non et la traite, le cas échéant. Vous pouvez accéder à l'API avec des appels REST, à l'aide de l'interface en ligne de commande kubectl ou d'autres outils en ligne de commande tels que kubeadm.

- **kube-scheduler**
Votre cluster est-il en bonne santé ? Est-il possible d'intégrer de nouveaux conteneurs si besoin ? Ce sont les questions auxquelles doit répondre le planificateur Kubernetes.

En plus de l'intégrité du cluster, le planificateur doit prendre en compte les besoins en ressources (par exemple, processeur ou mémoire) d'un pod. Il planifie ensuite l'attribution du pod au nœud de calcul adéquat.

- **kube-controller-manager**
Les contrôleurs assurent l'exécution du cluster, tandis que le gestionnaire de contrôleur Kubernetes regroupe plusieurs fonctions de contrôleur. Un contrôleur se réfère au planificateur pour s'assurer qu'un nombre suffisant de pods est exécuté. Si un pod est défaillant, un autre contrôleur le remarque et réagit. Un contrôleur connecte les services aux pods afin que les demandes soient acheminées jusqu'aux points de terminaison appropriés. D'autres contrôleurs permettent de créer des comptes et des jetons d'accès aux API.

- **etcd**
« etcd » est une base de données clé-valeur qui comprend les données de configuration et les informations sur l'état du cluster. Distribuée et résistante aux pannes, la base de données etcd constitue la référence unique concernant votre cluster.


*Une fois que vous aurez terminer cette partie d'introduction je vous invites à lire les différentes rubrique nous permettant de faire de l'administration sur Kubernetes.* \
*Nous proposons également un Tp pour voir comment il fonctionne*

## Authors

- [@Ulrich NOUMSI](https://www.linkedin.com/in/ulrich-steve-noumsi/)

