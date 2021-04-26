# ansible-role-configure-ssh

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
