Ansible role: Apt
=========
Base role for install apt packages, repositories and keys.

Role Variables
--------------
|  variable        |  default  |  description                      |
|------------------|-----------|-----------------------------------|
| apt.packages     | []        |  List of apt packages to install  |
| apt.keys         | []        |  List of apt keys to add          |
| apt.repositories | []        |  List of apt repositories to add  | 
     
Install Playbook
----------------
```bash
ansible-galaxy install moletti.apt
```

Example Playbook
----------------
```yaml
- hosts: all
  vars:
    apt:
      packages:
        - htop
        - nload
        - vim
      keys:
        - name: nginx
          url: https://nginx.org/keys/nginx_signing.key
      repositories:
        - name: nginx
          repo: "deb https://nginx.org/packages/mainline/{{ ansible_distribution | lower }}/ {{ ansible_distribution_release }} nginx"
  roles:
    - { role: moletti.apt, tags: apt }
```

LICENSE
-------
[MIT](/LICENSE)