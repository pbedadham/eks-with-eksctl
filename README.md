# eks-with-eksctl
This repository provides an example of deploying an Amazon Elastic Kubernetes Service (EKS) cluster using eksctl

## why eksctl? 
  * Simplicity and Ease of Use: eksctl is purpose-built specifically for creating and managing EKS clusters. It abstracts away much of the complexity of creating an EKS cluster and simplifies the process with straightforward commands and configurations. This makes it a great choice for users who want a quick and simple way to get an EKS cluster up and running without dealing with excessive configuration.

  * EKS-Specific Features: eksctl is designed to support all the latest features and updates of Amazon EKS. As a dedicated tool for EKS, it typically has quicker support for new EKS features, which might take a bit longer to be available in Terraform's EKS provider.

  * Native EKS Best Practices: eksctl follows native EKS best practices and recommendations by AWS, ensuring that you create a well-architected cluster that aligns with AWS's guidelines and security measures.

  * Abstraction of Infrastructure: eksctl abstracts the infrastructure management and focuses on the Kubernetes cluster itself. It allows users to concentrate more on Kubernetes-specific configurations rather than managing the underlying AWS resources.

  * Simplified Cluster Configuration: eksctl allows you to configure your EKS cluster using a YAML or JSON configuration file. This configuration file contains most of the common settings needed to create a cluster, reducing the complexity of the process.

  * Seamless Updates: eksctl simplifies updates and upgrades of your EKS cluster. It provides straightforward commands to update the Kubernetes version or change the node group configurations.

## Prerequisites
* [kubectl](https://kubernetes.io/docs/tasks/tools/)
* [aws-cli](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)
* [eksctl](https://eksctl.io/introduction/#installation)
* [AWS access credentials](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html)

## Steps
To create a basic cluster for testing, run:
```
eksctl create cluster --name=eks-demo
```
But, for Production,  create a cluster with a config file; this helps to keep configuration consistency, Reproducibility, Version Control, Modularity and Reusability, Documentation etc.

Clone this repository to your local machine.

Open a terminal window and navigate to the repository directory.

Edit the eksctl-demo.yaml file to include your desired cluster configuration. This file specifies the cluster name, region, node group configuration, and any add-ons.

Run the following command to create the EKS cluster:

```
eksctl create cluster -f eksctl-basic-demo.yaml
```

This will create an EKS cluster based on the configuration specified in the eksctl-demo.yaml file.

Verify that the cluster was created successfully by running the following command:

```
kubectl get nodes
```
This will list the worker nodes in the cluster.

To delete the cluster, run the following command:
```
eksctl delete cluster -f eksctl-basic-demo.yaml
```
This will delete the EKS cluster along with any associated resources.

### Conclusion
This example demonstrates how to deploy an EKS cluster using eksctl. You can customize the cluster configuration in the eksctl-basic-demo.yaml file to meet your specific requirements.
