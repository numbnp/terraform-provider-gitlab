---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "gitlab_project_tag Data Source - terraform-provider-gitlab"
subcategory: ""
description: |-
  The gitlab_project_tag data source allows details of a project tag to be retrieved by its name.
  Upstream API: GitLab API docs https://docs.gitlab.com/ee/api/tags.html
---

# gitlab_project_tag (Data Source)

The `gitlab_project_tag` data source allows details of a project tag to be retrieved by its name.

**Upstream API**: [GitLab API docs](https://docs.gitlab.com/ee/api/tags.html)

## Example Usage

```terraform
# By project ID
data "gitlab_project_tag" "foo" {
  name    = "example"
  project = "12345"
}

# By project full path
data "gitlab_project_tag" "foo" {
  name    = "example"
  project = "foo/bar"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String) The name of a tag.
- `project` (String) The ID or URL-encoded path of the project owned by the authenticated user.

### Optional

- `id` (String) The ID of this resource.

### Read-Only

- `commit` (Set of Object) The commit associated with the tag. (see [below for nested schema](#nestedatt--commit))
- `message` (String) The message of the annotated tag.
- `protected` (Boolean) Bool, true if tag has tag protection.
- `release` (Set of Object) The release associated with the tag. (see [below for nested schema](#nestedatt--release))
- `target` (String) The unique id assigned to the commit by Gitlab.

<a id="nestedatt--commit"></a>
### Nested Schema for `commit`

Read-Only:

- `author_email` (String)
- `author_name` (String)
- `authored_date` (String)
- `committed_date` (String)
- `committer_email` (String)
- `committer_name` (String)
- `id` (String)
- `message` (String)
- `parent_ids` (Set of String)
- `short_id` (String)
- `title` (String)


<a id="nestedatt--release"></a>
### Nested Schema for `release`

Read-Only:

- `description` (String)
- `tag_name` (String)


