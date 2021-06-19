Ansible role: Apt
=========
Base role for managing apt packages, repositories and keys.

Install
----------------
```bash
ansible-galaxy install moletti.apt
```

Example Playbook
----------------
```yaml
- hosts: all
  gather_facts: no
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
  roles:
    - { role: moletti.apt, tags: apt }
```


Role Variables
--------------
|  variable        | type         | default |
|------------------|--------------|---------|
| apt_packages     | list(dict)   | []      |
| apt_keys         | list(dict)   | []      |
| apt_repositories | list(dict)   | []      |



apt_packages:

|  Parameter                    |  required  |  default   |
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
| filename                     |  -          |            |
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
