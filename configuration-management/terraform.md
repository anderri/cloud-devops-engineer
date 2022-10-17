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

[https://www.youtube.com/watch?v=VpN0bW6Ej8g](https://www.youtube.com/watch?v=VpN0bW6Ej8g)

* Complex type&#x20;
  * Collection type (list, map, set) similar values
  * Structural type (tuple, object) dissimilar values&#x20;

Complex Types

<pre class="language-hcl" data-overflow="wrap"><code class="lang-hcl"><strong>// List 
</strong><strong>// Applications  
</strong>variable "planet" {
    type = list(string)
    default = ["mars", "earth", "moon"]
}
username = var.planet[0]</code></pre>

```hcl
// Maps - is like a data table 
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
// Set - differ from list 2 ways
// only 1 single type of value 
// doens't care for repetition or order
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
// Tuple - is like a group with differ type value
variable "my_tubple" {
    type = tuple([string,number,bool])
    default = ["hello", "42", "true"]
}
```





#### Built-In Functions

*   Numeric&#x20;

    * abs: returns the absolute value of number
    * floor: returns the closest whole number that is less than or equal to the given value, which may be a fraction
    * Log: returns the logarithm of a given number in a given base&#x20;
    * ceil: returns the closest whole number that is greater than or equal to the given value&#x20;
    * min: takes one or more numbers and returns the smallest number from the set
    * max: takes one or more numbers and returns the greatest number from the set&#x20;
    * parseint: parses the given string as a representation of an integer in the specified base and returns the resulting number
    * pow: calculates an exponent, by raising its first argument to the power of the second argument.&#x20;
    * signum: determines the sign of a number, returning a number between -1 and 1 to represent the sign.&#x20;


* String
  * chomp: removes newline characters at the end of a string.

```hcl
// chomp
chomp ("hello\n")
hello
chomp ("hello\r\n")
hello 
chomp ("hello\n\n")
hello 
```

* format: produces a string by formatting a number of other values according to a specification string.

```hcl
// format
format ("Hello, %s!", "Ander")
Hello, Ander!
# %s = string

format ("There are %d lights", 4)
There are 4 lights
# %d = digit 
```

* formatlist: produces a list of strings by formatting a number of other values according to a specification string.

```
// formatlist
formatlist ("Hello, %s!", ["Ander", "Olivia", "Sam"])
Hello, Ander!
Hello, Olivia!
Hello, Sam!
# %s = string

formatlist ("%s, %s!", "Salutations", ["Ander", "Olivia", "Sam"])
Salutations, Ander!
Salutations, Olivia!
Salutations, Sam!
# %s = string
```





* Collection
* Encoding
* Filesystem
* Data and Time
* Hash and Crypto
* IP Network
* Type Conversion



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

