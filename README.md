# Kubernetes Cluster Creation on Amazon EKS using eksctl

This repository contains a guide and code snippets for creating a Kubernetes cluster on Amazon EKS (Elastic Kubernetes Service) using eksctl, a command-line tool provided by AWS. The steps outlined below will help you set up a basic cluster with two worker nodes.

## Prerequisites

Before you begin, ensure that you have the following prerequisites in place:

- An AWS account with appropriate permissions to create resources on Amazon EKS.
- An IDE (Integrated Development Environment) set up and linked to your AWS account.

## Steps to Create the Kubernetes Cluster

Follow the steps below to create a Kubernetes cluster on Amazon EKS using eksctl:

1. **Install eksctl on your local machine**:
   - Install eksctl by following the official [eksctl installation guide](https://github.com/weaveworks/eksctl#installation).
   - Verify that eksctl is installed correctly by running `eksctl version` in your terminal.

2. **Link your AWS account to your IDE**:
   - Ensure that your IDE is properly linked to your AWS account. Refer to the documentation or resources specific to your IDE for detailed instructions on how to set up the AWS integration.

3. **Create the EKS cluster**:
   - Open your IDE and execute the following command in your terminal:
     ```bash
     eksctl create-cluster --name test-cluster --version 1.25 --region <your-region> --nodegroup-name linux-nodes --node-type t2.micro --nodes 2
     ```
     Replace `<your-region>` with the AWS region in which you want to create the cluster.

4. **Confirm worker node creation**:
   - Run the following command to verify that the worker nodes have been created and are available in the cluster:
     ```bash
     kubectl get nodes
     ```
     This command should display the information about the two worker nodes you created.

5. **Deleting the cluster**:
   - If you want to remove all the resources associated with the cluster, you can use eksctl to delete the cluster. Run the following command in your terminal:
     ```bash
     eksctl delete cluster --name test-cluster --region <your-region>
     ```
     Replace `<your-region>` with the AWS region where your cluster is located.

## Additional Resources

For more information about Amazon EKS, eksctl, or Kubernetes in general, consider referring to the following resources:

- [Amazon EKS Documentation](https://aws.amazon.com/eks/)
- [eksctl GitHub Repository](https://github.com/weaveworks/eksctl)
- [Kubernetes Documentation](https://kubernetes.io/docs/)


