---
title: "Kubernetes"
date: 2026-01-04
---


# Introduction
“Kubernetes” – does this term ring a bell? Especially to all the technology enthusiasts out there you must have heard or come across this term, If your answer is yes and you understand everything around it, you may give this concept a skip. For the rest who have heard the term and know briefly about it, stick around and browse through the sections as a refresher and for people who have not heard of this term or are not well versed, worry not, this blog will give you much information to get you started and interested.

The content is divided into 4 parts,

* History
* What is Kubernetes?
* Why Kubernetes?
* How to get started with Kubernetes?

# History
Before directly jumping into getting to knowing kubernetes, it is best to understand the evolution of deployments in the software industry. Software deployment is simply a way of running applications, traditionally they were run on physical servers. There were limitations in running application in physical servers which led to the inception of a concept called "Virtualization".

## What are the limitations/drawbacks of running application on physical servers?
One major disadvantage is the lack of ability of sharing resources among different processes easily. Cost also plays an important role, a physical server is pricey to maintain(inclusive of real estate and infra for cooling). Scaling up is not easy and time consuming.

## What is virtualization?
In simple terms it is a software which allows to deploy(create) multiple machines using resources of an underlying physical hardware(host).

Virtualization made software or app developments convenient but to further simplify software deployments the concept of container deployments came into existence. 

## What is container?
An application and its dependencies packaged into one portable unit which is also light weight is referred to as a container.

With the high rate of adoption of container deployments gave rise to widespread use of "kubernetes". So simply put without containers, kubernetes would not exist. 

Now with the above concepts in mind, let us proceed to address the main topic i.e.,\

# What is Kubernetes?
Kubernetes is an orchestrator which intelligently helps in managing multiple container applications spanning across many hosts.

# Why Kubernetes?
The main purpose of container is optimum resource utilization, kubernetes with its intelligence and orchestration help to achieve this across multiple hosts, thereby helping to unlock the purpose and potential of containerized applications.

# Kubernetes vs docker
![docker vs kubernetes]({{ "/assets/images/dockervskubernetes.png" | relative_url }})


Docker is a containerization platform which helps in building, implementing and running containerized applications limited to one docker instance per host os  whereas Kubernetes is much more, it is a platform for running and managing containers from many container runtimes and operates on a cluster level on many hosts. Docker is one of the many runtimes kubernetes supports.

# How to get started with kubernetes?
## Steps for mac

Install kubectl 
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/darwin/amd64/kubectl"
```

Check Installation
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/darwin/arm64/kubectl.sha256"
echo "$(cat kubectl.sha256)  kubectl" | shasum -a 256 --check
kubectl: OK
```

Make the kubectl binary executable.
```
chmod +x ./kubectl
```

Move the kubectl binary to a file location on your system PATH.
```
sudo mv ./kubectl /usr/local/bin/kubectl 
sudo chown root: /usr/local/bin/kubectl
```

Test to ensure the version you installed is up-to-date:
```
kubectl version --client
Client Version: v1.31.3
Kustomize Version: v5.4.2
```

Verify kubectl configuration
```
kubectl cluster-info
```

Once the setup is complete, cluster-information can be got. Let us understand more about kubernetes cluster in the next section.

# Kubernetes Cluster
![kube_cluster]({{ "/assets/images/kube_cluster.png" | relative_url }})


Kubernetes cluster is composed of two components,
* kuernetes nodes
* kubernetes control plane

Kubernetes node comprises of: 
* kubelet
* kubeporxy 
*container runtime

Kubernete control plane consists of 
* kubeapi server
* control manager (including optional cloud control manager)
* scheduler 
* etcd









# References
* https://kubernetes.io/docs/tutorials/kubernetes-basics/
* https://portworx.com/blog/kubernetes-vs-virtual-machines/
* https://www.atlassian.com/microservices/microservices-architecture/kubernetes-vs-docker#:~:text=Kubernetes%20can%20be%20used%20with,containers%20a%20week%20at%20scale.
* https://www.index.dev/blog/kubernetes-vs-docker
