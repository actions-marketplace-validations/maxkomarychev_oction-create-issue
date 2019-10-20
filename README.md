# Create an issue

"Oction" is a GitHub Action that implements a single call with 
[@octokit/request](https://www.npmjs.com/package/@octokit/request)
allowing easy interaction with GitHub REST APIs from your workflow.

Original documentation: https://developer.github.com/v3/issues/#create-an-issue

This action implements `POST` request to `/repos/{owner}/{repo}/issues`


# Quick start

```yaml
- uses: maxkomarychev/oction-create-issue@v0.6.1
  id: my_step_id
  with:
    token: <token value>
    title: <title value>
- name: Print outputs
  run: |
    echo ${{ steps.my_step_id.outputs.id }}
    echo ${{ steps.my_step_id.outputs.number }}
```


# Inputs

| Name | Is required | Description |
|---|---|---|
|token|true|Token to authenticate the request
|owner|false|owner parameter
|repo|false|repo parameter
|title|true|The title of the issue.
|body|false|The contents of the issue.
|assignee|false|Login for the user that this issue should be assigned to. _NOTE: Only users with push access can set the assignee for new issues. The assignee is silently dropped otherwise. **This field is deprecated.**_
|milestone|false|The `number` of the milestone to associate this issue with. _NOTE: Only users with push access can set the milestone for new issues. The milestone is silently dropped otherwise._
|labels|false|Labels to associate with this issue. _NOTE: Only users with push access can set labels for new issues. Labels are silently dropped otherwise._
|assignees|false|Logins for Users to assign to this issue. _NOTE: Only users with push access can set assignees for new issues. Assignees are silently dropped otherwise._

# Outputs

| Name | Description |
|---|---|
|id|`id` field of the response (if exists)|
|number|`number` field of the response (if exists)|

# Friendly octions:

* [oction-create-deployment-status](https://github.com/maxkomarychev/oction-create-deployment-status)
* [oction-create-deployment](https://github.com/maxkomarychev/oction-create-deployment)
* [create-issue-oction](https://github.com/maxkomarychev/create-issue-oction)
* [oction-create-release](https://github.com/maxkomarychev/oction-create-release)
* [oction-lock-issue](https://github.com/maxkomarychev/oction-lock-issue)
* [oction-unlock-issue](https://github.com/maxkomarychev/oction-unlock-issue)
