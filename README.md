# ansible-role-configure-ssh

<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-2-orange.svg?style=for-the-badge)](#contributors)
<!-- ALL-CONTRIBUTORS-BADGE:END -->
<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

[![GitHub Workflow Status](https://img.shields.io/github/workflow/status/DylanGore-FYP/ansible-role-configure-ssh/lint?label=Lint&logo=github&style=for-the-badge)](https://github.com/DylanGore-FYP/ansible-role-configure-ssh/actions/workflows/lint.yml)

An Ansible role to configure SSH and setup SSH keys for a given user.

## Role Variables

| Name                 | Type        | Default                  | Required | Description                               |
| -------------------- | ----------- | ------------------------ | -------- | ----------------------------------------- |
| ssh_require_key_auth | boolean     | true                     | No       | Require public key authentication for SSH |
| ssh_key_user         | string      | `{{ ansible_ssh_user }}` | No       | The user to add the keys to               |
| ssh_keys             | list-string | _Empty List_             | No       | The list of SSH keys to add               |

## Example Playbook

The example playbook below shows the basic usage of this role.

playbook.yml

```yaml
- hosts: servers
  become: true
  roles:
    - role: configure_ssh
      ssh_key_user: ubuntu
      ssh_keys:
        - '../files/key1.pub'
        - '../files/key2.pub'
```

requirements.yml

```yaml
- name: configure_ssh
  src: https://github.com/DylanGore-FYP/ansible-role-configure-ssh.git
  version: v1.0.0
```

## Commit Message Convention

This project uses [Gitmoji](https://gitmoji.dev/) for commit organisation. For more details see the [Gitmoji Repository](https://github.com/carloscuesta/gitmoji).

## Contributors

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/DylanGore"><img src="https://avatars.githubusercontent.com/u/2760449?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Dylan Gore</b></sub></a><br /><a href="https://github.com/DylanGore-FYP/ansible-role-configure-ssh/commits?author=DylanGore" title="Code">💻</a> <a href="https://github.com/DylanGore-FYP/ansible-role-configure-ssh/commits?author=DylanGore" title="Documentation">📖</a> <a href="#ideas-DylanGore" title="Ideas, Planning, & Feedback">🤔</a></td>
    <td align="center"><a href="https://github.com/mohittaneja7"><img src="https://avatars.githubusercontent.com/u/4126813?v=4?s=100" width="100px;" alt=""/><br /><sub><b>Mohit Taneja</b></sub></a><br /><a href="#ideas-mohittaneja7" title="Ideas, Planning, & Feedback">🤔</a></td>
  </tr>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification.
