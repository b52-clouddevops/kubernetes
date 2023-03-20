
# eksctl 

EKS Creation is a lengthy task and involes working with multiple knows. So the easiest way to create kubernetes cluster on AWS is by using a tool called as `EKSCTL`


 AWS EKS Cluster Creation is a lengthy task and it involves lot of preparation steps like 
	1) Performing the setup 
	2) Create Control Place
	3) Create Worker Nodes 
	4) Copy the config and then connect the cluster

All 4 involves lot of interactive commands and time. To avoid this there are some certain official tools which can make things better and we are going to 
use EKSCTL. EKSCTL is the official CLI of EKS.

It's a simple CLI Tool for creating EKS Clusters.

```

How to deal using EKSCTL
1) Install EKSCTL 
 curl https://gitlab.com/thecloudcareers/opensource/-/raw/master/lab-tools/terraform/eksctl/install.sh | bash

2) Now, EKSCTL has to authenticate with AWS to provision the EKS Cluster and for the same , the machine where you're executing needs to have the
IAM Role attached or supply access or secret key.

3) Use "eksctl create cluster --help option to create the cluster options#

    $  eksctl create cluster --name k8-test --version 1.22 --region us-east-1 --nodegroup-name k8-ng --node-type t3.micro --nodes 2

This creates the cluster and will copy the kubeconfig to the ~/.kube/config

    # now you should be able to connect to cluster as well
    # kubectl get nodes

```

### How to Delete the created cluster ?

EKS is a chargeable managed service. Ensure you delete them once you practice them. Use the below command to delete the cluster 
```
$ eksctl delete cluster clusterName --region us-east-1
```