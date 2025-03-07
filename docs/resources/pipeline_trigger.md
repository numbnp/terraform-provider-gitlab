---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "gitlab_pipeline_trigger Resource - terraform-provider-gitlab"
subcategory: ""
description: |-
  The gitlab_pipeline_trigger resource allows to manage the lifecycle of a pipeline trigger.
  Upstream API: GitLab REST API docs https://docs.gitlab.com/ee/api/pipeline_triggers.html
---

# gitlab_pipeline_trigger (Resource)

The `gitlab_pipeline_trigger` resource allows to manage the lifecycle of a pipeline trigger.

**Upstream API**: [GitLab REST API docs](https://docs.gitlab.com/ee/api/pipeline_triggers.html)

## Example Usage

```terraform
resource "gitlab_pipeline_trigger" "example" {
  project     = "12345"
  description = "Used to trigger builds"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `description` (String) The description of the pipeline trigger.
- `project` (String) The name or id of the project to add the trigger to.

### Optional

- `id` (String) The ID of this resource.

### Read-Only

- `token` (String, Sensitive) The pipeline trigger token.

## Import

Import is supported using the following syntax:

```shell
# GitLab pipeline triggers can be imported using an id made up of `{project_id}:{pipeline_trigger_id}`, e.g.
terraform import gitlab_pipeline_trigger.test 1:3
```
