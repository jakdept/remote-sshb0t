# remote_sshbot
genuinetools/sshb0t but Ansible and pulls the keys from the runner.
Also `remote_sshbot` because Ansible is ansible about naming.

https://docs.github.com/en/rest/reference/teams#list-team-members

https://docs.github.com/en/rest/reference/orgs

https://docs.gitlab.com/ee/api/members.html

Example config (JSON and yaml):

```yaml
remote_sshbot:
  github.com:
    allowed_users:
      - jakdept
    allowed_github_orgs:
      - example-org
    allowed_github_teams:
      example-org:
        - team-a
        - team-b
  gitlab.com:
    allowed_users:
      - jakdept
    allowed_gitlab-teams:
      - example-org
  additional_keys:
```

```json
{
  "remote_sshbot":{
    "github.com": {
      "users": [
        "jakdept"
      ],
      "github-orgs": [
        "example-org"
      ],
      "github-teams": {
        "example-org": [
          "team-a",
          "team-b"
        ]
      }
    },
    "gitlab.com":{
      "users": [
        "jakdept"
      ],
      "gitlab-teams": [
        "example-org"
      ]
    }
    "additional_keys":[]
  }
}
```

Yes, this namespaces everything within it's own var struct. Deal.