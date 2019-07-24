Ansible Role: pip
=========

Role to install (_by default_) `python3-pip` package  or `python-pip` package (_if  passed as var_)  on **Debian/Ubuntu** and **EL** systems.

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below (located in  `defaults/main.yml`):

```yaml
pip_app_package: python3-pip
pip_desired_state: present
pip_upgrade_version: latest
```



Variable `pip_app_package`: Defines the app to install i.e. **python3-pip** or **python-pip**

Variable `pip_desired_state`: Defined to dynamically chose whether to install (i.e. either `present` or `latest`) or uninstall (i.e. `absent`) the package.

Variable `pip_upgrade_version`: Defined to dynamically chose what version of pip (for 2.x and 3.x) to upgrade/downgrade to.

Dependencies
------------

None

Example Playbook
----------------

For default behaviour of role (i.e. installation of **python3-pip** package) in ansible playbooks.
```yaml
- hosts: servers
  roles:
    - role: darkwizard242.pip
```

For customizing behavior of role (i.e. installation of latest **python-pip** package instead of **python3-pip**) in ansible playbooks.
```yaml
- hosts: servers
  roles:
    - role: darkwizard242.pip
      vars:
        pip_app_package: python-pip
```
             
For customizing behavior of role (i.e. un-installation of **python3-pip** package) in ansible playbooks.
```yaml
- hosts: servers
  roles:
    - role: darkwizard242.pip
      vars:
        desired_state: absent
```      
         
License
-------

[MIT](https://github.com/darkwizard242/ansible-role-pip/blob/master/LICENSE)

Author Information
------------------

This role was created by [Ali Muhammad](https://www.linkedin.com/in/ali-muhammad-759791130/).