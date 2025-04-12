# Entorno Kubernetes para sitio web estático

Este repositorio contiene los manifiestos de Kubernetes necesarios para levantar un entorno local en Minikube que sirve un sitio web estático utilizando NGINX y volúmenes persistentes.

---

#Requisitos previos

- Docker https://www.docker.com/
- kubectl https://kubernetes.io/docs/tasks/tools/
- Minikube https://minikube.sigs.k8s.io/docs/start/
- Git https://git-scm.com/
- Editor de texto (VSCode)

#Estructura del proyecto

k8s-manifests/
├── deployment/
│   └── deployment.yaml
├── service/
│   └── service.yaml
└── volume/
    ├── pv.yaml
    └── pvc.yaml

#Pasos para levantar el entorno

Clonar repositorios:

git clone https://github.com/Mart1n-chamoy/static-website.git
   git clone https://github.com/Mart1n-chamoy/k8s-infra.git
   cd k8s-infra

   Comando para iniciar minikube:

   minikube start

Aplicar los manifiestos en orden:

   kubectl apply -f volume/pv.yaml
   kubectl apply -f volume/pvc.yaml
   kubectl apply -f deployment/deployment.yaml
   kubectl apply -f service/service.yaml

Acceder al sitio web con:

   http://localhost:30000

   o usar el comando:

   minikube service web-static-service

Verificación:

   comando para ver pods:

   kubectl get pods

   comando para ver servicios:

   kubectl get svc


- Sitio web: https://github.com/Mart1n-chamoy/static-website
- Manifiestos K8s: https://github.com/Mart1n-chamoy/k8s-infra
