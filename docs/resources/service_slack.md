---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "gitlab_service_slack Resource - terraform-provider-gitlab"
subcategory: ""
description: |-
  The gitlab_service_slack resource allows to manage the lifecycle of a project integration with Slack.
  Upstream API: GitLab REST API docs https://docs.gitlab.com/ee/api/integrations.html#slack-notifications
---

# gitlab_service_slack (Resource)

The `gitlab_service_slack` resource allows to manage the lifecycle of a project integration with Slack.

**Upstream API**: [GitLab REST API docs](https://docs.gitlab.com/ee/api/integrations.html#slack-notifications)

## Example Usage

```terraform
resource "gitlab_project" "awesome_project" {
  name             = "awesome_project"
  description      = "My awesome project."
  visibility_level = "public"
}

resource "gitlab_service_slack" "slack" {
  project      = gitlab_project.awesome_project.id
  webhook      = "https://webhook.com"
  username     = "myuser"
  push_events  = true
  push_channel = "push_chan"
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `project` (String) ID of the project you want to activate integration on.
- `webhook` (String) Webhook URL (ex.: https://hooks.slack.com/services/...)

### Optional

- `branches_to_be_notified` (String) Branches to send notifications for. Valid options are "all", "default", "protected", and "default_and_protected".
- `confidential_issue_channel` (String) The name of the channel to receive confidential issue events notifications.
- `confidential_issues_events` (Boolean) Enable notifications for confidential issues events.
- `confidential_note_events` (Boolean) Enable notifications for confidential note events.
- `id` (String) The ID of this resource.
- `issue_channel` (String) The name of the channel to receive issue events notifications.
- `issues_events` (Boolean) Enable notifications for issues events.
- `merge_request_channel` (String) The name of the channel to receive merge request events notifications.
- `merge_requests_events` (Boolean) Enable notifications for merge requests events.
- `note_channel` (String) The name of the channel to receive note events notifications.
- `note_events` (Boolean) Enable notifications for note events.
- `notify_only_broken_pipelines` (Boolean) Send notifications for broken pipelines.
- `notify_only_default_branch` (Boolean, Deprecated) This parameter has been replaced with `branches_to_be_notified`.
- `pipeline_channel` (String) The name of the channel to receive pipeline events notifications.
- `pipeline_events` (Boolean) Enable notifications for pipeline events.
- `push_channel` (String) The name of the channel to receive push events notifications.
- `push_events` (Boolean) Enable notifications for push events.
- `tag_push_channel` (String) The name of the channel to receive tag push events notifications.
- `tag_push_events` (Boolean) Enable notifications for tag push events.
- `username` (String) Username to use.
- `wiki_page_channel` (String) The name of the channel to receive wiki page events notifications.
- `wiki_page_events` (Boolean) Enable notifications for wiki page events.

### Read-Only

- `job_events` (Boolean) Enable notifications for job events. **ATTENTION**: This attribute is currently not being submitted to the GitLab API, due to https://github.com/xanzy/go-gitlab/issues/1354.

## Import

Import is supported using the following syntax:

```shell
# You can import a gitlab_service_slack.slack state using the project ID, e.g.
terraform import gitlab_service_slack.slack.email 1
```
