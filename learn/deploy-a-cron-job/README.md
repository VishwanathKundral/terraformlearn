# Deploy a cron job

AWS

## scene

1. VPC, Security Groups, Subnet, EKS/Kubernetes
2. Qovery resources:
  1. Org `Terraform Demo`
  2. Project `cron-job`
  3. Envi `production`
  4. App `cron-job`
3. Builds `echo app`
4. Pushes `echo app` image in ECR registry
5. Deploys and run

## use

```shell
export TF_VAR_aws_access_key_id=YOUR_AWS_ACCESS_KEY_ID \
TF_VAR_aws_secret_access_key=YOUR_AWS_SECRET_ACCESS_KEY \
TF_VAR_qovery_access_token=YOUR_QOVERY_API_TOKEN \
TF_VAR_qovery_organization_id=YOUR_QOVERY_ORG_ID
```

Edit the `main.tf` file and change:
- Resource `resource "qovery_job" "cron-job"` field `source.git_repository.url` (=`https://github.com/Qovery/terraform-provider-testing.git`) with actial
- Resource `resource "qovery_job" "cron-job"` field `source.git_repository.branch` (=`job-echo-n-seconds`) with actual

Run the Terraform commands

```shell
terraform init
```

```shell
terraform plan
```

```shell
terraform apply
```
 
run `terraform destroy` to clear.
