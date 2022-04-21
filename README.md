# cloudreach.com

Provision Azure AKS Cluster using Terraform

Step-01: Introduction
Create SSH Keys for AKS Linux VMs
Declare Windows Username, Passwords for Windows nodepools. This needs to be done during the creation of cluster for 1st time itself if you have plans for Windows workloads on your cluster
Understand about Datasources and Create Datasource for Azure AKS latest Version
Create Azure Log Analytics Workspace Resource in Terraform
Create Azure AD AKS Admins Group Resource in Terraform
Create AKS Cluster with default nodepool
Create AKS Cluster Output Values
Provision Azure AKS Cluster using Terraform
Access and Test using Azure AKS default admin --admin
Access and Test using Azure AD User as AKS Admin


Step-02: Create 3 more Terraform Input Vairables to variables.tf
SSH Public Key for Linux VMs
Windows Admin username
Windows Admin Password


Step-03: Create Azure AD Group for AKS Admins Terraform Resource
To enable AKS AAD Integration, we need to provide Azure AD group object id.
We wil create a Azure Active Directory group for AKS Admins
# Create Azure AD Group in Active Directory for AKS Admins
resource "azuread_group" "aks_administrators" {
  name        = "${azurerm_resource_group.aks_rg.name}-cluster-administrators"
  description = "Azure AKS Kubernetes administrators for the ${azurerm_resource_group.aks_rg.name}-cluster."
}



Step-04: Create AKS Cluster Terraform Resource
Create a file named 07-aks-cluster.tf
Understand and discuss about the terraform resource named azurerm_kubernetes_cluster
This is going to be a very big terraform template when compared to what we created so far we will do it slowly step by step.4



Step-05: Create Terraform Output Values for AKS Cluster
Create a file named 08-outputs.tf



Step-6: Verify Resources using Azure Management Console
Resource Group
terraform-aks-dev
terraform-aks-dev-nrg
AKS Cluster & Node Pool
Cluster: terraform-aks-dev-cluster
AKS System Pool
Log Analytics Workspace
Azure AD Group
terraform-aks-dev-cluster-administrators
