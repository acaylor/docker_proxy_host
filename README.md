Docker proxy host
=========

This will install and configure docker and a few containers to make management easier.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

- geerlingguy.firewall
- geerlingguy.docker
- geerlingguy.pip
- community.docker

Pull dependencies with ansible-galaxy:
`ansible-galaxy install -r meta/requirements.yml`

Example Playbook
----------------

```yaml
---
- hosts: all
  become: yes
  vars:
    mysql_pw: "password"
    mysql_root_pw: "differentpassword"
    firewall_allowed_tcp_ports:
      - "22"
      - "80"
      - "81"
      - "443"
    firewall_allowed_udp_ports:
      - "51820"
    pip_install_packages:
      - name: docker
  roles:
    - docker_proxy_host
```

License
-------

BSD

Author Information
------------------

acaylor
