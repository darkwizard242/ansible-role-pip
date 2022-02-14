![Ansible Role](https://img.shields.io/ansible/role/42282?color=dark%20green%20) ![Ansible Role](https://img.shields.io/ansible/role/d/42282?label=role%20downloads) ![Ansible Quality Score](https://img.shields.io/ansible/quality/42282?label=ansible%20quality%20score) ![GitHub tag (latest SemVer)](https://img.shields.io/github/tag/darkwizard242/ansible-role-pip?label=release) ![GitHub repo size](https://img.shields.io/github/repo-size/darkwizard242/ansible-role-pip?color=orange&style=flat-square)

# Ansible Role: pip

Role to install (_by default_) [python3-pip package or python-pip package](https://pip.pypa.io/en/stable/) (_if passed as var_) on **Debian/Ubuntu** and **EL** systems.

## Requirements

None.

## Role Variables

Available variables are listed below (located in `defaults/main.yml`)

### Variables list:

```yaml
pip_app_package: python3-pip
pip_desired_state: present
pip_upgrade_version: latest
```

### Variables table:

Variable            | Description
------------------- | ------------------------------------------------------------------------------------------------------------------------------
pip_app_package     | Defined to dynamically provide package name i.e. **python3-pip** or **python-pip**
pip_desired_state   | Defined to dynamically select whether to install (i.e. either `present` or `latest`) or uninstall (i.e. `absent`) the package.
pip_upgrade_version | Defined to dynamically select whether to upgrade pip after installation or not.

## Dependencies

None

## Example Playbook

For default behaviour of role (i.e. installation of **python3-pip** package) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.pip
```

For customizing behavior of role (i.e. installation of latest **python-pip** package instead of **python3-pip**) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.pip
  vars:
    pip_app_package: python-pip
```

For customizing behavior of role (i.e. un-installation of **python3-pip** package) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.pip
  vars:
    desired_state: absent
```

## License

[MIT](https://github.com/darkwizard242/ansible-role-pip/blob/master/LICENSE)

## Author Information

This role was created by [Ali Muhammad](https://www.alimuhammad.dev/).
