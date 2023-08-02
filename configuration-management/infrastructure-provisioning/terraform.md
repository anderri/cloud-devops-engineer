# Terraform

#### Installation and Configuration Guide

* Install ->AWS CLI
* Install -> Terraform
* Install -> Git Desktop
* Install -> MS Visual Studio
* On Terminal -> aws configure (add profiles like DEV, TEST, QA, PROD)
* Save terraform backend on S3 + dynamo DB on Main AWS account&#x20;
*

#### Terraform AWS Config&#x20;

#### Install Terraform + autocomplete &#x20;

#### [https://learn.hashicorp.com/tutorials/terraform/install-cli#install-terraform](https://learn.hashicorp.com/tutorials/terraform/install-cli#install-terraform) 

#### Terraform Basics

* main.tf
* Init and Get
* Fmt, Validate, Console
* Plan and Apply
* Generate and configure AWS Credentials
* Create Input Variables
* Set Locals
* Create Outputs&#x20;



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

## Complex Types

### Collection Type

* **List**: Its like an array, you use an integer as the index to retrieve the value. ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 11.28.10 am.png>)
* **Maps** (data table): Its like a ruby hash or single nested json object. You use a key as the index to retrieve the value.\
  &#x20;![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 11.30.41 am.png>)
* **Set**: Is similar to a list but has no secondary index or preserved ordering, all values must of the same type and will be cast to match based on the first element. ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 11.33.32 am.png>)



### Structural Type

* **Object:** A structural type allows multiple values of several distinct type to be grouped together as a single value. Structural types a schema as an argument, to specify which types are allowed for which elements. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.13.24 pm.png>)
* **Tuple:** \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.24.12 pm.png>)
* **Map (data table):** \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.22.15 pm.png>)



#### Built-In Functions

*   **Numeric**&#x20;

    * **abs:** returns the absolute value of a number.\
      ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.27.30 pm.png>)
    * **floor:** returns the closest whole number that is less than or equal to the given value, which may be a fraction.\
      ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.27.50 pm.png>)
    * **Log:** returns the logarithm of a given number in a given base.![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.35.05 pm.png>)&#x20;
    * **ceil:** returns the closest whole number that is greater than or equal to the given value.\
      ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.35.45 pm.png>) &#x20;
    * **min:** takes one or more numbers and returns the smallest number from the set.
    * **max:** takes one or more numbers and returns the greatest number from the set.
    * **parseint:** parses the given string as a representation of an integer in the specified base and returns the resulting number.\
      &#x20;![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.36.39 pm.png>)
    * **pow:** calculates an exponent, by raising its first argument to the power of the second argument.\
      ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.38.22 pm.png>)&#x20;
    * **signum:** determines the sign of a number, returning a number between -1 and 1 to represent the sign.\
      &#x20;![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.38.46 pm.png>)







* **String**
  * **Chomp:** removes newline characters at the end of a string. \
    ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.39.50 pm.png>)
  * **Format:** produces a string by formatting a number of other values according to a specification string. \
    ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.40.56 pm.png>)
  * **formatlist:** produces a list of strings by formatting a number of other values according to a specification string. \
    ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.41.59 pm.png>)
  * **indent:** adds a given number of spaces to the beinnings of all but the first line in a given-line string. \
    ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.44.55 pm.png>)
  * **join:** produces a string by concatenating together all elements of a given list of things with the given delimiter. \
    ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.45.49 pm.png>)
  * **lower:** converts all cased letters in given string to lowercase. \
    ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.46.31 pm.png>)
  * **upper:** converts all case letters in the given string to uppercase.&#x20;
  * **regex (regular expression):** applies a regular expression to a string and returns the matching substrings.\
    ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.47.03 pm.png>)
  * **regexall (regular expression):** applies a regular expression to a string and returns a list of all matches.
  * **replace:** searches a given string for another given substring, and replaces each occurrence with a given replacement string.\
    &#x20;![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.48.43 pm.png>)
  * **split:** produces a list by dividing a given string at all occurrences of a given separator. \
    ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.49.44 pm.png>)
  * **strreve:** reverses the characters in a string.\
    ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.50.12 pm.png>)&#x20;
  * **substr:** extracts a substring from a given string by offset and length. \
    ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.50.47 pm.png>)
  * **title:** converts the first letter of each word in the given string to uppercase.\
    ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.52.08 pm.png>)
  * **trim:** removes the specified characters from the start and end of the given string. \
    ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.52.34 pm.png>)
  * **trimprefix:** removes the specified prefix from the start of the given string. IF the string does not start with the prefix, the string is returned unchanged.&#x20;
  * **trimsuffix:** removes the specified suffix from the end of the given string.
  * **trimspace:** removes all type of whitespaces from both the start and the end of a string.&#x20;

### Collection

* **alltrue (operator and):** returns true if all elemetns in given collection are true or "true". It also returns true if the collection is empty. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 11.19.14 am.png>)
* **anytrue (operator or):** returns true if any element in a given collection is true or "true". It also returns false if the collection is empty.\
  &#x20;![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 11.18.24 am.png>)\

* **chunklist:** splits a single list into fixed-size chinks, returning a list of lists.![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 11.20.08 am.png>)\

* **coalesce:** takes any number of arguments and returns the first one that isn't null or empty string. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 11.23.37 am.png>)\

* **coalescelist:** takes any number of list arguments and returns the first one that isn't empty. ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 11.24.08 am.png>)
* **compact:** Takes a list of strings and returns a new list with any empty string elements removed. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.55.18 pm.png>)
* **concat:** Takes two or more lists and combines them into a single list.\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.56.19 pm.png>)
* **contains:** Determines whether a given list or set contains a given single value as one of its elements. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.57.34 pm.png>)
* **distinct:** Takes a list a returns a new list with any duplicate elements removed. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 1.58.59 pm.png>)
* **element:** Retrieves a single element from a list. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 2.00.03 pm.png>)
* **index:** Finds the element index for a given value in a list. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 2.01.06 pm.png>)
* **flatten:** Takes a list and replaces any elements that are lists with a flattened sequence of the list contents. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 2.02.20 pm.png>)
* **keys:** Takes a map and returns a list containing the keys from that map.\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 2.03.27 pm.png>)
* **length:** Determines the length of a given list, map, or string. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 2.05.11 pm.png>)
* **lookup:** Retrieves the value of a single element from a map, given its key. If the given key does not exist, the given default value is returned instead. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 2.07.53 pm.png>)
* **matchkeys:** Constructs a new list by taking a subset of elements from one list whose indexes match the corresponding indexes of values in another list. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 2.12.17 pm.png>)
* **merge:** Takes an arbitrary number of maps or objetcs, and returns a single map or object that contains a merged set of elements from all arguments.\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 2.18.52 pm.png>)
* **one:** Takes a list, set, or tuple value with either zero or one elements. If the collection is empty, one returns null. Otherwise, one returns the first element. If there are two or more elements then one will return an error. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.03.18 pm.png>)
* **range:** Generates a list of numbers using a start value, a limit value, and a step value.\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.05.20 pm.png>)
* **reverse:** Takes a sequence and produces a new sequence of the same length with all of the same elements as the given sequence but in reverse order. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.08.28 pm.png>)
* **setintersection:** Function takes multiple sets and produces a single set containing only the elements that all of the given sets have in common. In other words, it computes the intersection of the sets.\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.11.22 pm.png>)
* **setproduct:** Function finds all the possible combinations of elements from all of the given sets by computing the Cartesian product. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.13.56 pm.png>)
* **setsubtract:** Function returns a new set containing the elements from the first set that are not present in the second set. In other words, it computes the relative complement of the first set in the second set. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.15.34 pm.png>)
* **setunion:** Function takes multiple sets and produces a single set containing the elements from all of the given sets. In other words, it computes the union of the sets. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.17.38 pm.png>)
* **slice:** Extracts some consecutive elements from within a list. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.19.00 pm.png>)
* **sort:** Takes a list of strings and returns a new list with those strings sorted lexicographically.\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.20.37 pm.png>)
* **sum:** Takes a list of set and returns the sum of those numbers.\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.24.04 pm.png>)
* **transpose:** Takes a map of list of strings and swaps the key and value to produce a new map of lists of strings.\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.24.48 pm.png>)
* **value:** Take a map and return a list containing the values of the elements in that map.\
  &#x20;![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.25.16 pm.png>)
* **zapmap:** Constructs a map from a list of keys and a corresponding list of values. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.25.24 pm.png>)

#### Encoding and Decoding Functions

![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.31.53 pm.png>)

* **Encode:**
  * base64encode
  * jsonencode
  * yamlencode
  * textencodebase64
  * base64gzip
  * urlencode\
    ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.36.17 pm.png>)\

*   **Decode:**

    * base64decode
    * jsondecode
    * textdecodebase64
    * yamldecode
    * cvsdecode



#### Filesystem Functions&#x20;

* **abspath:** Takes a string containing a filesystem path and converts it to an absolute path. That is, if the path is not absolute, it will be joined with the current working directory. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.38.56 pm.png>)
* **dirname:** Takes a string containing a filesystem path and removes the last portion from it.\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.41.32 pm.png>)
* **basename:** Takes a string containing a filesystem path and removes all except the last portion from it. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.44.06 pm.png>)
* **pathexpand:** Takes a filesystem path that might begin with a \~ segment, and if so it replaces that segment with the current user's home directory path. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.42.07 pm.png>)
* **file:** Reads the contents of a file at the given path and returns them as a string. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.45.20 pm.png>)
* **fileexists:** Determines whether a file exists at a given path. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 7.48.23 pm.png>)
* **fileset:** Enumerates a set of regular file names given a path and pattern. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.06.05 pm.png>)
* **filebase64:** Reads the contents of a file at the given path and returns them as a base64-encoded string. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.07.50 pm.png>)
* templatefile: Reads the file at the given path and renders its content as a template using a supplied set of template variables.\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.09.27 pm.png>)\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.15.39 pm.png>)
*

#### Data and Time Functions

* **formatdate:** Converts a timestamp into a different time format.\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.18.22 pm.png>)
* **timeadd:** Adds a duration to a timestamp, returning a new timestamp. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.18.53 pm.png>)
* **timestamp:** Returns a UTC timestamp string in RFC 3339 format. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.19.13 pm.png>)



#### Hash and Crypto

Generate hashes and cryptographic strings.&#x20;

* **bcrypt:**![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.21.19 pm.png>)
* **base64sha256**
* **base64sha512**
* **filebase64sha256**
* **filebase64sha512**
* **filemd5**
* **filesha256**
* **filesha512**
* **md5**
* **rsadecrypt**
* **sha1**
* **sha256**
* **sha512**
* **uuid**
* **uuidv5**

&#x20;

#### IP Network **Functions**

* **cidrhost:** Calculates a full host IP address for a given host number within a given IP network address prefix. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.26.48 pm.png>)
* **cidrnetmask:** Converts an IPv4 address prefix given in CIDR notation into a subnet mask address. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.28.16 pm.png>)
* **cidrsubnet:** Calculates a subnet address within given IP network address prefix.\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.29.27 pm.png>)
* **cidrsubnets:** Calculates a sequence of consecutive IP address ranges within a particular CIDR prefix. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.31.03 pm.png>)

#### Type Conversion Functions

* **can:** Evaluates the given expression and returns a boolean value indication whether the expression produced a result without any errors. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.36.03 pm.png>)
* **defaults:** A specialized function intended for use with input variables whose type constraints are object types or collections of object types that include optional attributes. \

* **nonsensitive:** Takes a sensitive value and returns a copy of that value with the sensitive marking removed, thereby exposing the sensitive value. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.37.28 pm.png>)
* **sensitive:** Takes any value and returns a copy of it marked so that Terraform will treat it as sensitive, with the same meaning and behavior as far sensitive input variables. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.37.49 pm.png>)
* **tobool:** Converts its argument to a boolean value.\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.41.48 pm.png>)
* **tomap:** Converts its argument to a map value.\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.42.09 pm.png>)
* **toset:** Converts its argument to a set value.\
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.42.27 pm.png>)
* **tolist:** Converts its argument to a list value. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.42.44 pm.png>)
* **tonumber:** Converts its argument to a number value. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.42.54 pm.png>)
* **tostring:** Converts its argument to a set value. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.43.07 pm.png>)
* **try:** Evaluates all of its argument expressions in turn and return the result of the first one that does not produce any errors. \
  ![](<../../.gitbook/assets/Screen Shot 2022-10-18 at 8.43.46 pm.png>)

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



#### Terraform workspace

{% embed url="https://www.youtube.com/watch?v=JmfEKEYdxKU&t=987s" %}



```
// Terraform Workspace Commands

terraform workspace list 

terraform workspace new dev

terraform workspace new qa

terraform workspace new prod


```

#### Migrate local to remote workspace



#### Move AWS Credentials to Env Vars&#x20;

\
\
\


### Questions for exam

{% embed url="https://learn.hashicorp.com/collections/terraform/certification" %}

{% embed url="https://www.whizlabs.com/blog/terraform-certification-exam-questions/" %}

{% embed url="https://www.freecram.net/question/HashiCorp.TA-002-P.v2021-12-18.q113/if-a-module-uses-a-local-variable-you-can-expose-that-value-with-a-terraform-output" %}

{% embed url="https://www.freecram.net/exam/TA-002-P-hashicorp-certified-terraform-associate-e11859.html" %}

{% embed url="https://medium.com/bb-tutorials-and-thoughts/250-practice-questions-for-terraform-associate-certification-7a3ccebe6a1a" %}

{% embed url="https://www.udemy.com/course/terraform-associate-practice-exam/" %}

{% embed url="https://www.freecram.net/pdf/TA-002-P.pdf" %}

