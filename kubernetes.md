## Kubernetes


### Install
 
__Kubectl__

```sh
# OS X
brew install kubectl
# or
curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/darwin/amd64/kubectl

# Linux
curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl

# Windows
curl -LO https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/windows/amd64/kubectl.exe


chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
```


__Minikube__

https://github.com/kubernetes/minikube/releases

```sh
# OS X
curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.18.0/minikube-darwin-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/

# Linux
curl -Lo minikube https://storage.googleapis.com/minikube/releases/v0.18.0/minikube-linux-amd64 && chmod +x minikube && sudo mv minikube /usr/local/bin/

sudo mv minikube /usr/local/bin
```

Some docs [kubernetes.io/docs/home](https://kubernetes.io/docs/home/)


 * [MiniKube](https://kubernetes.io/docs/getting-started-guides/minikube/): Install a single-node Kubernetes cluster on your local machine for development and testing.
 * [Kops](https://kubernetes.io/docs/getting-started-guides/kops/): Bring up a complete Kubernetes cluster on Amazon Web Services, using a tool called kops.
 * [Kubeadm](https://kubernetes.io/docs/getting-started-guides/kubeadm/) (Beta): Install a secure Kubernetes cluster on any pre-existing machines running Linux, using the built-in kubeadm tool.
 * [Kargo](https://kubernetes.io/docs/getting-started-guides/kargo/): Deploy a Kubernetes cluster on-premise baremetal or hosted on cloud providers, with Ansible and kargo tools.


### Kops

```sh
# OS X
brew update && brew install --HEAD kops

# Source
go get -d k8s.io/kops
cd ${GOPATH}/src/k8s.io/kops/
git checkout release
make
```



### Concepts

 * The __Kubernetes Master__ is a collection of three processes that run on a single node in your cluster, which is designated as the master node. Those processes are: _kube-apiserver_, _kube-controller-manager_ and _kube-scheduler_.
 * Each individual non-master node in your cluster runs two processes:
   * _kubelet_ - which communicates with the Kubernetes Master.
   * _kube-proxy_ - a network proxy which reflects Kubernetes networking services on each node.
