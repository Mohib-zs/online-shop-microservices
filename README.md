### Initialize the backend
    Run the backend script (Convert to .sh first if you're using linux or wsl)
### Initialize Vnet Module
     Go to vnet module and setup the terraform.tfvars file.
     Fill the values from the variables.tf file accordingly.
     Run Terraform init and Terraform apply.
### Initialize Aks Module
     Perform the same steps in the aks module as well
### Get Aks Credentials
     Set the same subscription which you used to setup the infrastucture
     Run this command "az aks get-credentials --resource-group <"resource group name"> --name <"Cluster name"> --admin --overwrite-existing"
     perform kubelogin as well if required "kubelogin convert-kubeconfig -l azurecli"
### Deployed the microservices
     Deploy the microservices using either config.yaml or helmfile.yaml or install.sh
### Access the Application
     Run "kubectl get svc -w"
     Wait a few minutes until the cluster assigns a loadbalancer ip to front-end service.
     Enter the IP in the browser and access the application
     If it doesn't assign an ip then check the logs of the front-end serivce to see if there is a permission or an allocation issue.
