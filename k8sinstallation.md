---
id: install k8s
title: installing k8s using kubeadm
---

## Step1: Installing Docker
```
cat EOF<< install-docker.sh >
sudo apt-get remove docker docker-engine docker.io containerd runc .
sudo apt-get update .
sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    gnupg-agent \
    software-properties-common .
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add - .
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable" .
sudo apt-get update .
sudo apt-get install docker-ce docker-ce-cli containerd.io . 
EOF
bash install-docker.sh
```

## Step2: Install kubeadm, kubectl, and kubelet
```
sudo apt-get update && sudo apt-get install -y apt-transport-https curl
curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -
sudo cat <<EOF | sudo tee /etc/apt/sources.list.d/kubernetes.list
deb https://apt.kubernetes.io/ kubernetes-xenial main
EOF
sudo apt-get update
sudo apt-get install -y kubelet kubeadm kubectl
sudo apt-mark hold kubelet kubeadm kubectl
```

## Step3: Initialization
```
sudo kubeadm init --pod-network-cidr=192.168.0.0/16 --apiserver-advertise-address=<ipv6> --apiserver-cert-extra-sans <public-ip>,<dns-name>

run the three steps it will display in terminal in master
```

## Step4: Install Calico for Networking
```
kubectl apply -f https://docs.projectcalico.org/v3.14/manifests/calico.yaml
```

## Step5: Join the nodes with cluster
```
kubeadm join command in nodes with master ip address.
```