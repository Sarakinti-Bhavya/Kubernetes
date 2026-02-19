# Kubernetes Cluster Creation
Goal

**Create and access a managed Kubernetes cluster on AWS using EKS.****
What is EKS?

Amazon EKS-AWS managed Kubernetes service.

AWS manages:

  -Control plane(  API Server,  Scheduler,  etcd)

User manages:

  -Worker nodes (EC2)
  -Applications

 ** Tools Used**
 1️⃣ Ubuntu (WSL)

Used Linux environment inside Windows.

wsl -d Ubuntu

2️⃣ AWS CLI

Used to authenticate AWS account.

Install + verify:
sudo apt install unzip
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
aws --version
Configure:
aws configure

3️⃣ kubectl

kubectl-Used to interact with Kubernetes cluster.
Install + Verify:
curl -o kubectl https://amazon-eks.s3.us-west-2.amazonaws.com/1.19.6/2021-01-05/bin/linux/amd64/kubectl
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin
kubectl version --client

4️⃣ eksctl

eksctl

Tool that automates EKS creation.

Install+ Verify:
curl --silent --location "https://github.com/weaveworks/eksctl/releases/latest/download/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
sudo mv /tmp/eksctl /usr/local/bin
eksctl version
**Creating EKS Cluster**
Command used:

eksctl create cluster \
--name my-eks-cluster \
--region ap-south-1 \
--nodegroup-name workers \
--node-type t3.micro \
--nodes 2

✅ Cluster Verification

Check nodes:

kubectl get nodes


Output:

2 worker nodes (Ready)
**Delete Cluster After Practice**
eksctl delete cluster \
--region ap-south-1 \
--name my-eks-cluster
