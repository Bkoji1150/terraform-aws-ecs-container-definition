# terraform-aws-ecs-container-definition

Using terraform to create and manage ecs task-definition

This module builds the infrastructure for **hqr-operational-enviroment** agen in the **REPORTING-BACKEND** cell.

This module was built using [Jenkins-SonarQube-Terraform](git@github.com:Bkoji1150/Jenkins-SonarQube-Terraform.git).

## Usage 
```hcl
module "container" {
  source          = "../../"
  container_name  = "name"
  container_image = "cloudposse/geodesic"

  environment = [
    {
      name  = "string_var"
      value = "I am a string"
    },
    {
      name  = "true_boolean_var"
      value = true
    },
    {
      name  = "false_boolean_var"
      value = false
    },
    {
      name  = "integer_var"
      value = 42
    }
  ]

  port_mappings = [
    {
      containerPort = 8080
      hostPort      = 80
      protocol      = "tcp"
    },
    {
      containerPort = 8081
      hostPort      = 443
      protocol      = "udp"
    }
  ]
}

```

<!-- prettier-ignore-start -->
<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->

## Authors

Module is maintained by [kOJI BELLO](https://github.com/antonbabenko) with help from [these awesome contributors](https://github.com/terraform-aws-modules/terraform-aws-autoscaling/graphs/contributors).
