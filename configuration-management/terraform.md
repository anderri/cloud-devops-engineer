# Terraform

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
* Creat Outputs&#x20;



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

* **List**: Its like an array, you use an integer as the index to retrieve the value. ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 11.28.10 am.png>)
* **Maps** (data table): Its like a ruby hash or single nested json object. You use a key as the index to retrieve the value.\
  &#x20;![](<../.gitbook/assets/Screen Shot 2022-10-18 at 11.30.41 am.png>)
* **Set**: Is similar to a list but has no secondary index or preserved ordering, all values must of the same type and will be cast to match based on the first element. ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 11.33.32 am.png>)



### Structural Type

* **Object:** A structural type allows multiple values of several distinct type to be grouped together as a single value. Structural types a schema as an argument, to specify which types are allowed for which elements. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.13.24 pm.png>)
* **Tuple:** \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.24.12 pm.png>)
* **Map (data table):** \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.22.15 pm.png>)



#### Built-In Functions

*   **Numeric**&#x20;

    * **abs:** returns the absolute value of a number.\
      ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.27.30 pm.png>)
    * **floor:** returns the closest whole number that is less than or equal to the given value, which may be a fraction.\
      ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.27.50 pm.png>)
    * **Log:** returns the logarithm of a given number in a given base.![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.35.05 pm.png>)&#x20;
    * **ceil:** returns the closest whole number that is greater than or equal to the given value.![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.35.45 pm.png>) &#x20;
    * **min:** takes one or more numbers and returns the smallest number from the set.
    * **max:** takes one or more numbers and returns the greatest number from the set.
    * **parseint:** parses the given string as a representation of an integer in the specified base and returns the resulting number.\
      &#x20;![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.36.39 pm.png>)
    * **pow:** calculates an exponent, by raising its first argument to the power of the second argument.\
      ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.38.22 pm.png>)&#x20;
    * **signum:** determines the sign of a number, returning a number between -1 and 1 to represent the sign.\
      &#x20;![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.38.46 pm.png>)



****

****

* **String**
  * **Chomp:** removes newline characters at the end of a string. \
    ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.39.50 pm.png>)
  * **Format:** produces a string by formatting a number of other values according to a specification string. \
    ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.40.56 pm.png>)
  * **formatlist:** produces a list of strings by formatting a number of other values according to a specification string. \
    ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.41.59 pm.png>)
  * **indent:** adds a given number of spaces to the beinnings of all but the first line in a given-line string. \
    ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.44.55 pm.png>)
  * **join:** produces a string by concatenating together all elements of a given list of things with the given delimiter. \
    ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.45.49 pm.png>)
  * **lower:** converts all cased letters in given string to lowercase. \
    ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.46.31 pm.png>)
  * **upper:** converts all case letters in the given string to uppercase.&#x20;
  * **regex (regular expression):** applies a regular expression to a string and returns the matching substrings.\
    ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.47.03 pm.png>)
  * **regexall (regular expression):** applies a regular expression to a string and returns a list of all matches.
  * **replace:** searches a given string for another given substring, and replaces each occurrence with a given replacement string.\
    &#x20;![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.48.43 pm.png>)
  * **split:** produces a list by dividing a given string at all occurrences of a given separator. \
    ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.49.44 pm.png>)
  * **strreve:** reverses the characters in a string.\
    ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.50.12 pm.png>)&#x20;
  * **substr:** extracts a substring from a given string by offset and length. \
    ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.50.47 pm.png>)
  * **title:** converts the first letter of each word in the given string to uppercase.\
    ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.52.08 pm.png>)
  * **trim:** removes the specified characters from the start and end of the given string. \
    ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.52.34 pm.png>)
  * **trimprefix:** removes the specified prefix from the start of the given string. IF the string does not start with the prefix, the string is returned unchanged.&#x20;
  * **trimsuffix:** removes the specified suffix from the end of the given string.
  * **trimspace:** removes all type of whitespaces from both the start and the end of a string.&#x20;

### Collection

* **alltrue (operator and):** returns true if all elemetns in given collection are true or "true". It also returns true if the collection is empty. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 11.19.14 am.png>)
* **anytrue (operator or):** returns true if any element in a given collection is true or "true". It also returns false if the collection is empty.\
  &#x20;![](<../.gitbook/assets/Screen Shot 2022-10-18 at 11.18.24 am.png>)\

* **chunklist:** splits a single list into fixed-size chinks, returning a list of lists.![](<../.gitbook/assets/Screen Shot 2022-10-18 at 11.20.08 am.png>)\

* **coalesce:** takes any number of arguments and returns the first one that isn't null or empty string. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 11.23.37 am.png>)\

* **coalescelist:** takes any number of list arguments and returns the first one that isn't empty. ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 11.24.08 am.png>)
* **compact:** Takes a list of strings and returns a new list with any empty string elements removed. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.55.18 pm.png>)
* **concat:** Takes two or more lists and combines them into a single list.\
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.56.19 pm.png>)
* **contains:** Determines whether a given list or set contains a given single value as one of its elements. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.57.34 pm.png>)
* **distinct:** Takes a list a returns a new list with any duplicate elements removed. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 1.58.59 pm.png>)
* **element:** Retrieves a single element from a list. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 2.00.03 pm.png>)
* **index:** Finds the element index for a given value in a list. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 2.01.06 pm.png>)
* **flatten:** Takes a list and replaces any elements that are lists with a flattened sequence of the list contents. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 2.02.20 pm.png>)
* **keys:** Takes a map and returns a list containing the keys from that map.\
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 2.03.27 pm.png>)
* **length:** Determines the length of a given list, map, or string. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 2.05.11 pm.png>)
* **lookup:** Retrieves the value of a single element from a map, given its key. If the given key does not exist, the given default value is returned instead. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 2.07.53 pm.png>)
* **matchkeys:** Constructs a new list by taking a subset of elements from one list whose indexes match the corresponding indexes of values in another list. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 2.12.17 pm.png>)
* **merge:** Takes an arbitrary number of maps or objetcs, and returns a single map or object that contains a merged set of elements from all arguments.\
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 2.18.52 pm.png>)
* **one:** Takes a list, set, or tuple value with either zero or one elements. If the collection is empty, one returns null. Otherwise, one returns the first element. If there are two or more elements then one will return an error. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 7.03.18 pm.png>)
* **range:** Generates a list of numbers using a start value, a limit value, and a step value.\
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 7.05.20 pm.png>)
* **reverse:** Takes a sequence and produces a new sequence of the same length with all of the same elements as the given sequence but in reverse order. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 7.08.28 pm.png>)
* **setintersection:** Function takes multiple sets and produces a single set containing only the elements that all of the given sets have in common. In other words, it computes the intersection of the sets.\
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 7.11.22 pm.png>)
* **setproduct:** Function finds all the possible combinations of elements from all of the given sets by computing the Cartesian product. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 7.13.56 pm.png>)
* **setsubtract:** Function returns a new set containing the elements from the first set that are not present in the second set. In other words, it computes the relative complement of the first set in the second set. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 7.15.34 pm.png>)
* **setunion:** Function takes multiple sets and produces a single set containing the elements from all of the given sets. In other words, it computes the union of the sets. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 7.17.38 pm.png>)
* **slice:** Extracts some consecutive elements from within a list. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 7.19.00 pm.png>)
* **sort:** Takes a list of strings and returns a new list with those strings sorted lexicographically.\
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 7.20.37 pm.png>)
* **sum:** Takes a list of set and returns the sum of those numbers.\
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 7.24.04 pm.png>)
* **transpose:** Takes a map of list of strings and swaps the key and value to produce a new map of lists of strings.\
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 7.24.48 pm.png>)
* **value:** Take a map and return a list containing the values of the elements in that map.\
  &#x20;![](<../.gitbook/assets/Screen Shot 2022-10-18 at 7.25.16 pm.png>)
* **zapmap:** Constructs a map from a list of keys and a corresponding list of values. \
  ![](<../.gitbook/assets/Screen Shot 2022-10-18 at 7.25.24 pm.png>)
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

