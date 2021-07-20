
Ansible role: Apt
=========
[![Ansible Role](https://img.shields.io/ansible/role/54865)](https://galaxy.ansible.com/moletti/apt) 
[![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/moletti/ansible-role-apt)](https://github.com/moletti/ansible-role-apt/releases)
[![Ansible Quality Score](https://img.shields.io/ansible/quality/54865)](https://galaxy.ansible.com/moletti/apt)
[![Ansible Role](https://img.shields.io/ansible/role/d/54865)](https://galaxy.ansible.com/moletti/apt)

Base role for managing apt packages, repositories and keys.


Role install
----------------
```bash
ansible-galaxy install moletti.apt
```

Example Playbook
----------------
```yaml
- hosts: all
  gather_facts: yes
  vars:
    apt_packages:
      - name: ['htop', 'nload', 'vim']
      - name: ['nano', 'less']
        state: latest
    apt_keys:
      - url: https://nginx.org/keys/nginx_signing.key
    apt_repositories:
      - filename: nginx
        repo: "deb https://nginx.org/packages/mainline/{{ ansible_distribution | lower }}/ {{ ansible_distribution_release }} nginx"
    apt_sources:
      - "deb http://deb.debian.org/debian/ {{ ansible_distribution_release }} main"
      - "deb http://security.debian.org/debian-security {{ ansible_distribution_release }}/updates main"
  roles:
    - { role: moletti.apt, tags: apt }
```


Role Variables
--------------
|  variable        | type         | default | description                                  |
|------------------|--------------|---------|----------------------------------------------|
| apt_packages     | list(dict)   | []      | Manages apt packages                         |
| apt_keys         | list(dict)   | []      | Manages apt keys                             |
| apt_sources      | list(string) | []      | Manages apt sources ( /etc/apt/source.list ) |
| apt_repositories | list(dict)   | []      | Manages apt repositories                     |



apt_packages:

|  Parameter                   |  required  |  default   |
|------------------------------|------------|------------|
| allow_unauthenticated        |  -         |            |
| autoclean                    |  -         |            |
| autoremove                   |  -         |            |
| cache_valid_time             |  -         | **3600**   |
| deb                          |  -         |            |
| default_release              |  -         |            |
| dpkg_options                 |  -         |            |
| force                        |  -         |            |
| force_apt_get                |  -         | **true**   |
| install_recommends           |  -         |            |
| name                         |  -         |            |
| only_upgrade                 |  -         |            |
| policy_rc_d                  |  -         |            |
| purge                        |  -         |            |
| state                        |  -         |            |
| update_cache                 |  -         | **true**   |
| update_cache_retries         |  -         |            |
| update_cache_retry_max_delay |  -         |            |
| upgrade                      |  -         |            |

apt_keys:

|  Parameter     |  required  |  default   |
|----------------|------------|------------|
| data           |  -         |            |
| file           |  -         |            |
| id             |  -         |            |
| keyring        |  -         |            |
| keyserver      |  -         |            |
| state          |  -         |            |
| url            |  -         |            |
| validate_certs |  -         |            |

apt_repositories:

|  Parameter                   |  required   | default    |
|------------------------------|-------------|------------|
| codename                     |  -          |            |
| filename                     |  +          |            |
| install_python_apt           |  -          |            |
| mode                         |  -          |            |
| repo                         |  +          |            |
| state                        |  -          |            |
| update_cache                 |  -          |            |
| update_cache_retries         |  -          |            |
| update_cache_retry_max_delay |  -          |            |
| validate_cert                |  -          |            |

LICENSE
-------
[MIT](/LICENSE)
