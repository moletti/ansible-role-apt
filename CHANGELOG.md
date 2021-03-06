# Changelog

# [2.5.0](https://github.com/moletti/ansible-role-apt/compare/v2.4.1...v2.5.0) (2021-08-08)


### Bug Fixes

* Fix apt_preferences explanation ([f3572e8](https://github.com/moletti/ansible-role-apt/commit/f3572e88e0aa0ee356fe65f36744bf1474bdde92))
* Fix variable naming ([1fcd439](https://github.com/moletti/ansible-role-apt/commit/1fcd43998b5e08e29b71f5d8e95a28278ce1ddc2))


### Features

* Add global postfix, remove_unmanaged, remove_mode variables ([5dcaa62](https://github.com/moletti/ansible-role-apt/commit/5dcaa6211a2da7c0537c26db9bbad2e7a9a1b45e))
* Add preferences_unmanaged ([39c6f6a](https://github.com/moletti/ansible-role-apt/commit/39c6f6a05b1db129c230e6332801c2d48591c001))

## [2.4.1](https://github.com/moletti/ansible-role-apt/compare/v2.4.0...v2.4.1) (2021-07-31)


### Bug Fixes

* Remove duplicate code ([76885fc](https://github.com/moletti/ansible-role-apt/commit/76885fcbd0fb4de5d178e34d65c3af579c5329e2))

# [2.4.0](https://github.com/moletti/ansible-role-apt/compare/v2.3.0...v2.4.0) (2021-07-30)


### Features

* Add apt_repositories_exclude ([73b8bc5](https://github.com/moletti/ansible-role-apt/commit/73b8bc548bd82a377d49783438dec989075d76a6))

# [2.3.0](https://github.com/moletti/ansible-role-apt/compare/v2.2.0...v2.3.0) (2021-07-29)


### Features

* Add remove mode postfix for apt_repositories ([f498b2b](https://github.com/moletti/ansible-role-apt/commit/f498b2b7f9c7179d9b5890baa17a747c4724b6d8))
* Remove unmanaged repositories ([3f6d3c4](https://github.com/moletti/ansible-role-apt/commit/3f6d3c4ee265cce63005093711fc2ad0e01664fc))

# [2.2.0](https://github.com/moletti/ansible-role-apt/compare/v2.1.0...v2.2.0) (2021-07-24)


### Features

* Add support apt_preferences ([2af18c5](https://github.com/moletti/ansible-role-apt/commit/2af18c5a81c136dd67b3f73e88a60e6b33083ea9))

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
