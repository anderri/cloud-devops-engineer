# Terraform

#### Install Terraform + autocomplete &#x20;

#### [https://learn.hashicorp.com/tutorials/terraform/install-cli#install-terraform](https://learn.hashicorp.com/tutorials/terraform/install-cli#install-terraform)

####

\


#### Terraform Basics

* main.tf
* Init and Get
* Fmt, Validate, Console
* Plan and Apply
* Generate and configure AWS Credentials
* Create Input Variables
* Set Locals
* Creat Outputs



####

#### &#x20;



Terraform Provisioners

Terraform Providers

Terraform Language

Variables and Data

Resource Meta Arguments

Terraform Expressions

Terraform State

Infrastructure Drift

Terraform Troubleshooting

Terraform Modules

Team Workflows

Terraform Backends



#### Resources and Complex Types

* Complex type&#x20;
  * Collection type (list, map, set) similar values
  * Structural type (tuple, object) dissimilar values&#x20;

Complex Types

<pre class="language-hcl" data-overflow="wrap"><code class="lang-hcl"><strong>// List 
</strong>variable "planet" {
    type = list
    default = ["mars", "earth", "moon"]
}
username = var.planet[0]</code></pre>

```hcl
// Maps - like table 
variable "plans" {
    type = maps
    default = {
        "PlanA = "10 USD"
        "PlanB = "50 USD"
        "PlanC = "100 USD"
    }
}
username = var.plans["PlanB"]
```

```hcl
// Set
> toset(["a","b",c])
[
    "a",
    "b",
    "3",
]
```

Structural Type

```hcl
variable "with_optional_attribute" {
    type = object ({
        a = string # a required attribute 
        b = optional(string) #an optional attribute
    })      
```

```hcl
// Tuple - list group
variable "my_tubple" {
    type = tuple([string,number,bool])
    default = ["hello", "42", "true"]
}
```





Built-In Functions

Terraform Cloud

Terraform Enterprise

&#x20;Workspaces

Packer and Terraform

Consul and Terraform

Vault and Terraform

Alantis, CDK for Terraform, GruntWork, Terragrunt, TerraTest

Booking Your Exam



####



#### Use a Terraform Module



#### Divide project into multiplo files



#### Terraform destroy



#### Create a Terraform workspace



#### Migrate local to remote workspace



#### Migrate local to remote workspace



#### Move AWS Credentials to Env Vars&#x20;



&#x20;

