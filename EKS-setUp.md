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
aws --version
Configure:
aws configure
3️⃣ kubectl

kubectl-Used to interact with Kubernetes cluster.
Verify:

kubectl version --client
4️⃣ eksctl

eksctl

Tool that automates EKS creation.

Verify:

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
