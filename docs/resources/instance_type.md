---
page_title: "morpheus_instance_type Resource - terraform-provider-morpheus"
subcategory: ""
description: |-
  Provides a Morpheus instance type resource
---

# morpheus_instance_type

Provides a Morpheus instance type resource

## Example Usage

```terraform
resource "morpheus_instance_type" "tf_example_instance_type" {
  name               = "tf_example_instance"
  code               = "tf_example_instance"
  description        = "Terraform Example Instance Type"
  category           = "web"
  visibility         = "private"
  image_path         = "tfexample.png"
  image_name         = "tfexample.png"
  featured           = false
  enable_deployments = true
  enable_scaling     = true
  enable_settings    = true
  environment_prefix = "TFEXAMPLE_DEMO"
  option_type_ids    = [1910, 1912]

  evar {
    name   = "first"
    value  = "first"
    export = true
  }

  evar {
    name         = "second"
    masked_value = "second"
    export       = false
  }
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- **category** (String) The instance type category (web, sql, nosql, apps, network, messaging, cache, os, cloud, utility)
- **code** (String) The instance type code
- **name** (String) The name of the instance type
- **visibility** (String) The visibility of the instance type (public or private)

### Optional

- **description** (String) The description of the instance type
- **enable_deployments** (Boolean) Whether to enable deployments for the instance type
- **enable_scaling** (Boolean) Whether to enable scaling for the instance type
- **enable_settings** (Boolean) Whether to enable settings for the instance type
- **environment_prefix** (String) The prefix used for instance environment variables
- **evar** (Block List) The environment variables to create (see [below for nested schema](#nestedblock--evar))
- **featured** (Boolean) Whether the instance type is marked as featured
- **image_name** (String) The file name of the instance type logo image
- **image_path** (String) The file path of the instance type logo image including the file name
- **option_type_ids** (List of Number) The IDs of the inputs to associate with the instance type

### Read-Only

- **id** (String) The ID of the instance type

<a id="nestedblock--evar"></a>
### Nested Schema for `evar`

Optional:

- **export** (Boolean) Whether the environment variable is exported as an instance tag
- **masked_value** (String, Sensitive) The environment variable value when the value needs to be masked
- **name** (String) The name of the environment variable
- **value** (String) The environment variable value when the value can be in plaintext

## Import

Import is supported using the following syntax:

```shell
terraform import morpheus_instance_type.tf_example_instance_type 1
```