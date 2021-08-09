# Contributing 

## Submitting a Pull Request
1. Fork the project
2. Clone your fork
3. Make your code changes
4. Push your branch up to your fork
5. Open a pull requests 

## Codeing rules
### Commit message guidelines
If possible, make automic commits. A commit should contain exactly one self-contained functional change.

### Commit message format
```
<type>: <subject>
``` 

#### Type
The type must be one of the following:

| Type         | Description                                                                                                 |
|--------------|-------------------------------------------------------------------------------------------------------------|
| **ci**       | Changes to our CI configuration files and scripts (example: GitHub Action) |
| **docs**     | Documentation only changes                                                                                  |
| **feat**     | A new feature                                                                                               |
| **fix**      | A bug fix                                                                                                   |
| **perf**     | A code change that improves performance                                                                     |
| **refactor** | A code change that neither fixes a bug nor adds a feature                                                   |
| **style**    | Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)      |
| **test**     | Adding missing tests or correcting existing tests                                                           |

#### Examples

```
feat: Add apt_repositories support
```
```
fix: Add missing dependencies
```

### Working with code
#### Tests
```bash
pip3 install -r requirements.txt
molecule test
```
#### Lint
```bash
molecule lint
```
or
```bash
yamllint -c .yamllint . && ansible-lint -c .ansible-lint .
```