### Terraform Infrastructure Provisionin for DEV/PROD environments:

Using terraform workspaces to deploy to development and production environments
```
### Provisioning
$ terraform workspace new prod
$ terraform workspace new dev

$ terraform workspace select dev
$ terraform apply -var-file=dev.tfvars

$ terraform workspace select prod
$ terraform apply -var-file=prod.tfvars

### Test 
$ git clone https://github.com/GoogleCloudPlatform/microservicesdemo.git
$ gcloud container clusters get-credentials dev-gke-cluster --zone us-west1-a --project <PROJECT_ID>
$ kubectl apply -f ./microservices-demo/release/kubernetesmanifests.yaml
$ kubectl get service frontend-external | awk '{print $4}'

```

### Note
If you are using a **service account** for this exercise, make sure that the *IAM Service Account Credentials API* is enabled and that you have the *Service Account Token Creator* role.

If you encounter any issue, try running it in the *Cloud Shell* first.
