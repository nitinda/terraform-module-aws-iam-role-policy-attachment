# _Terraform Module: terraform-module-iam-role-policy-attachment_


## _General_

_Terraform module Provides an_ **_IAM Role Policy Attachment_** _resources in AWS cloud provider..._

---


## _Prerequisites_

_This module needs_ **_Terraform 0.12.18_** _or newer._
_You can download the latest Terraform version from_ [_here_](https://www.terraform.io/downloads.html).

_This module deploys aws services details are in respective feature branches._

---

## _Features_

_Below we are able to check the resources that are being created as part of this module call:_

* **_IAM Role Policy Attachment_**


---

## _Usage_

## _Using this repo_

_To use this module, add the following call to your code:_

```tf
module "iam_role_policy_attachment" {
  source = "git::https://github.com/nitinda/terraform-module-aws-iam-role-policy-attachment.git?ref=master"

  providers = {
    aws = aws.services
  }

  ## IAM Role Policy
  role       = var.role
  policy_arn = var.policy_arn

}
```

```tf
module "iam_role_policy_attachment" {
  source = "git::https://github.com/nitinda/terraform-module-aws-iam-role-policy-attachment.git?ref=master"

  providers = {
    aws = aws.services
  }

  ## IAM Role Policy
  role       = module.iam_role.name
  policy_arn = "arn:aws:iam::aws:policy/service-role/AmazonEC2RoleforSSM"

}
```
---

## _Inputs_

_The variables required in order for the module to be successfully called from the deployment repository are the following:_

|**_Variable_** | **_Description_** | **_Type_** | **_Argument Status_** |
|:----|:----|-----:|:---:|
| **_role_** | _The role name the policy should be applied to_ | _string_ | **_Required_** |
| **_policy\_arn_** | _The ARN of the policy you want to apply_ | _string_ | **_Required_** |


---

## _Outputs_

### _General_

_This module has the following outputs:_

* **_N/A_**


---

### _Usage_

_In order for the variables to be accessed at module level please use the syntax below:_

```tf
module.<module_name>.<output_variable_name>
```


_The output variable is able to be accessed through terraform state file using the syntax below:_

```tf
data.terraform_remote_state.<layer_name>.<output_variable_name>
```

---

## _Authors_

_Module maintained by Module maintained by the -_ **_Nitin Das_**
