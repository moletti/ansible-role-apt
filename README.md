
Ansible role: Apt
=========
[![Ansible Role](https://img.shields.io/ansible/role/54865)](https://galaxy.ansible.com/moletti/apt) [![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/moletti/ansible-role-apt)](https://github.com/moletti/ansible-role-apt/releases) [![GitHub Workflow Status](https://img.shields.io/github/workflow/status/moletti/ansible-role-apt/Ansible%20Molecule?label=test)](https://github.com/moletti/ansible-role-apt/actions/workflows/molecule.yml) [![Ansible Quality Score](https://img.shields.io/ansible/quality/54865)](https://galaxy.ansible.com/moletti/apt) [![Ansible Role](https://img.shields.io/ansible/role/d/54865)](https://galaxy.ansible.com/moletti/apt)

Base role for managing apt packages, repositories, keys, sources and preferences.


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
    apt_repositories_remove_unmanaged: true
    apt_sources:
      - "deb http://deb.debian.org/debian/ {{ ansible_distribution_release }} main"
      - "deb http://security.debian.org/debian-security {{ ansible_distribution_release }}/updates main"
    apt_preferences:
      - package: 'some_package'
        filename: 'some'
        pin: 'release a=testing'
        priority: 800
  roles:
    - { role: moletti.apt, tags: apt }
```


Role Variables
--------------
|  variable                          | type         | default                    | description                                                  |
|------------------------------------|--------------|----------------------------|--------------------------------------------------------------|
| apt_packages                       | list(dict)   | []                         | Manages apt packages                                         |
| apt_keys                           | list(dict)   | []                         | Manages apt keys                                             |
| apt_sources                        | list(string) | []                         | Manages apt sources ( /etc/apt/source.list )                 |
| apt_postfix                        | string       | _ansible                   | Global apt postfix                                           |
| apt_remove_unmanaged               | bool         | false                      | Remove all unmanaged resources ( repositories, preferences, etc ) |
| apt_remove_mode                    | string       | default                    | If set by "default" remove all resources that are not in the "apt_resource". If set "postfix" remove all resource that are not match regular expression ".*{{ apt_resources_postfix }}{{ apt_resources_ext }}" |
| apt_repositories                   | list(dict)   | []                         | Manages apt repositories                                     |
| apt_repositories_postfix           | string       | {{ apt_postfix }}          | Apt repositories postfix                                     |
| apt_repositories_remove_unmanaged  | bool         | {{ apt_remove_unmanaged }} | Remove all unmanaged repositories ( /etc/apt/source.list.d ) |
| apt_repositories_remove_mode       | string       | {{ apt_remove_mode }}      | If set by "default" remove all repositories that are not in the "apt_repositories". If set "postfix" remove all repositories that are not match regular expression ".*{{ apt_repositories_postfix }}.list" |
| apt_repositories_exclude           | list(string) | []                         | Exclude files from deletion                                  |
| apt_preferences                    | list(dict)   | []                         | Manages apt preferences                                      |
| apt_preferences_postfix            | string       | {{ apt_postfix }}          | Apt preferences postfix                                      |
| apt_preferences_remove_unmanaged   | bool         | {{ apt_remove_unmanaged }} | Remove all unmanaged preferences ( /etc/apt/preferences.d/ ) |
| apt_preferences_remove_mode        | string       | {{ apt_remove_mode }}      | If set by "default" remove all preferences that are not in the "apt_preferences". If set "postfix" remove all preferences that are not match regular expression ".*{{ apt_preferences_postfix }}.list" |
| apt_preferences_exclude            | list(string) | []                         | Exclude files from deletion                                  |

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

apt_preferences:

|  Parameter                   |  required   | default    |
|------------------------------|-------------|------------|
| filename                     |  +          |            |
| package                      |  -          | *          |
| pin                          |  +          |            |
| priority                     |  +          |            |
| state                        |  -          | present    |
| explanation                  |  -          |            |

LICENSE
-------
[MIT](/LICENSE)
