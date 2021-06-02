Ansible role: Apt
=========
Base role for install apt packages, repositories and keys.

Role Variables
--------------
|  variable        | type         | default |  description                      |
|------------------|--------------|---------|-----------------------------------|
| apt_packages     | list(dict)   | []      |  List of apt packages to install  |
| apt_keys         | list(dict)   | []      | List of apt keys to add           |
| apt_repositories | list(dict)   | []      | List of apt repositories to add   |

apt_packages:

|  variable        |  required  |  description                           |
|------------------|------------|----------------------------------------|
| name             | +          | A list of package names                |
| state            | -          | Indicates the desired package state.   |

apt_keys:

|  variable        |  required  |  description                           |
|------------------|------------|----------------------------------------|
| id               | -          | The identifier of the key.             |
| url              | +          |  The URL to retrieve key from.         |
| keyring          | -          | The full path to specific keyring file |

apt_repositories:

|  variable        |  required  |  description                                             |
|------------------|------------|----------------------------------------------------------|
| repo             | +          | A source string for the repository.                      |
| filename         | -          | Sets the name of the source list file in sources.list.d. |


     
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
    apt_packages:
      - name:
          - htop
          - nload
          - vim
      - name:
          - nano
          - less
        state: latest
    apt_keys:
      - url: https://nginx.org/keys/nginx_signing.key
    apt_repositories:
      - repo: "deb https://nginx.org/packages/mainline/{{ ansible_distribution | lower }}/ {{ ansible_distribution_release }} nginx"
  roles:
    - { role: moletti.apt, tags: apt }
```

LICENSE
-------
[MIT](/LICENSE)