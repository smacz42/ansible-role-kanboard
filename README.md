# Ansible Role: `kanboard`

## Description

This role installs a kanboard instance on CentOS7. It can optionally use a mysql database.

#### NOTE: Role is not yet configured for upgrade or migration functionality - only for initial installs.

### Operating Systems:

* CentOS7

### Dependencies

* `smacz42.common`
* `smacz42.iptables`
* `smacz42.httpd`
* `smacz42.mysql`

## Default Role Variables

```yaml
kanboard_mysql: true # Use mysql for database. `sqlite` if 'false'
kanboard_debug: true # Generate php `debug.log` in data directory if 'true'
```

## Example Playbook

```yaml
- name: Install Kanboard on CentOS7
  hosts: all
  gather_facts: yes

  roles:
    - { role: smacz42.common }
    - { role: smacz42.iptables }
    - { role: smacz42.httpd }
    - { role: smacz42.mysql, when: kanboard_mysql }
    - { role: kanboard }
```

## License

Licensed under the MIT License. See the LICENSE file for details.

## Author Information

This role was created in YYYY by [Andrew Cz](andrewcz.com), a student at The Ohio State University.
