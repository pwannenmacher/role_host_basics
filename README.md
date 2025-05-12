# Host Basics

Configures hostname and installs and configures some useful packages

## Requirements

none

## Role Variables

| Variable                       | Required | Default                                                                                                               | Choices | Comments |
|--------------------------------|----------|-----------------------------------------------------------------------------------------------------------------------|---------|----------|
| host_basic_default_packages    | yes      | `[ufw, htop, mc, nmap, nano, curl, net-tools, openssh-client, python3-pip, git, rsync, libffi-dev, libssl-dev, tree]` |         |          |
| host_basic_additional_packages | yes      | `[]`                                                                                                                  |         |          |
| timezone                       | yes      | "Etc/UTC"                                                                                                             |         |          |
| ufw_enabled                    | yes      | false                                                                                                                 |         |          |
| hostname                       | yes      | `{{ inventory_hostname }}`                                                                                            |         |          |

## Dependencies

Only default modules are used. No dependencies.

## Example Playbook

```yaml
- hosts: all
  become: true
  vars:
    host_basic_additional_packages:
      - some_package
  roles:
    - role: role_host_basics
```

## License

MIT

## Author Information

Paul Wannenmacher
