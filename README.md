ansible-lighthouse-role
=========
Ansible Role for VK LightHouse software. LightHouse is a lightweight GUI interface for ClickHouse. 

Requirements
------------
The role use the git application. You should install git in ansible pre-task. 

Role Variables
--------------
F: You can specify a install directory
```
lighthouse_dir: "/var/www/lighthouse"
```

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------
```
- name: Install LIGHTHOUSE
  hosts: lighthouse-01
  tags: lighthouse
  pre_tasks:
    - name: Install GIT
      become: true
      ansible.builtin.apt:
        update_cache: yes
        package: "{{ item }}"
      with_items:
        - git
  roles:
    - lighthouse
```
License
-------

BSD

Author Information
------------------

AirDRoN
