# Changelog

# [2.1.0](https://github.com/moletti/ansible-role-apt/compare/v2.0.0...v2.1.0) (2021-07-20)


### Bug Fixes

* Fix apt_dependencies ([9a48a45](https://github.com/moletti/ansible-role-apt/commit/9a48a45c36f830645031f5d4041a8eb604fbf8ce))


### Features

* Add Ubuntu support ([4ae9520](https://github.com/moletti/ansible-role-apt/commit/4ae952059251f15608324d7dcec682ac7e2f1a72))

# [2.0.0](https://github.com/moletti/ansible-role-apt/compare/v1.2.0...v2.0.0) (2021-07-19)


### Bug Fixes

* Add galaxy_info.namespace & Set the min_ansible_version type to string ([c4dc8e8](https://github.com/moletti/ansible-role-apt/commit/c4dc8e80c497b6e127b4d3f1909c081cc0dc028b))
* Fix ansible-lint no-handler ([d4de86a](https://github.com/moletti/ansible-role-apt/commit/d4de86a5d1d726b06d8620b858d55885afade2b5))
* Fix collection dependencies for molecule ([4e2fdf2](https://github.com/moletti/ansible-role-apt/commit/4e2fdf2431b8b4b065eaa7025fef921619637299))
* Fix converge ([9ae2fd2](https://github.com/moletti/ansible-role-apt/commit/9ae2fd200bf52d3e7c87b2619c41ad1b319c3845))
* Fix variable name in templates/source.list.j2 ([7398766](https://github.com/moletti/ansible-role-apt/commit/73987669209e3a39fab3c34dffb7514c9a9cc243))


### Features

* Add role argument validation ([e2a5ea3](https://github.com/moletti/ansible-role-apt/commit/e2a5ea3dc1b21ae42a74fb8edfad6222202d5c4f))
* Set filename is required for apt_repositories ([5f065de](https://github.com/moletti/ansible-role-apt/commit/5f065defd0db3cef12a682cb8849849cb9d1069a))


### BREAKING CHANGES

* filename in apt_repository is required for features future
* Upgrade min_ansible_version from 2.10 to 2.11

# [1.2.0](https://github.com/moletti/ansible-role-apt/compare/v1.1.0...v1.2.0) (2021-06-20)


### Bug Fixes

* ansible-lint warnings ([601e666](https://github.com/moletti/ansible-role-apt/commit/601e666445c7d8693648ab4dbb459f4a14b25cb4))


### Features

* Add support source.list ([eac1c65](https://github.com/moletti/ansible-role-apt/commit/eac1c655e8f2bb05d35be8dcbf241d3e2025e0f5))

# [1.1.0](https://github.com/moletti/ansible-role-apt/compare/v1.0.0...v1.1.0) (2021-06-19)


### Features

* Automatically versioning via semantic-release ([16b4053](https://github.com/moletti/ansible-role-apt/commit/16b4053532af3a040aa796c16a94ae59d44966d3))
