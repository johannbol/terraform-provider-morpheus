---
page_title: "morpheus_operational_workflow Resource - terraform-provider-morpheus"
subcategory: ""
description: |-
  Provides a Morpheus operational workflow resource.
---

# morpheus_operational_workflow

Provides a Morpheus operational workflow resource.

## Example Usage

```terraform
resource "morpheus_operational_workflow" "tf_example_operational_workflow" {
  name                = "tf_example_operational_workflow"
  description         = "Terraform operational workflow example"
  platform            = "all"
  visibility          = "private"
  allow_custom_config = true
  option_types = [
    1730
  ]
  task_ids = [18]
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- **name** (String) The name of the operational workflow

### Optional

- **allow_custom_config** (Boolean) Allow a custom configuration to be supplied
- **description** (String) The description of the operational workflow
- **option_types** (List of Number) The option types associated with the operational workflow
- **platform** (String) The operating system platforms the operational workflow is supported to run on
- **task_ids** (List of Number) A list of tasks ids associated with the operational workflow
- **visibility** (String) Whether the operational workflow is visible in sub-tenants or not

### Read-Only

- **id** (Number) The ID of the operational workflow

## Import

Import is supported using the following syntax:

```shell
terraform import morpheus_operational_workflow.tf_example_operational_workflow 1
```