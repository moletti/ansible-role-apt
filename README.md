Ansible role: Apt
=========
Base role for install apt packages, repositories and keys.

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
