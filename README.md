# ansible-macos-atom
Ansible role to manage a atom installation on macOS.

[![Build Status](https://img.shields.io/travis/feffi/ansible-macos-atom.svg)](https://travis-ci.org/feffi/ansible-macos-atom) [![Github All Releases](https://img.shields.io/github/downloads/feffi/ansible-macos-atom/total.svg)](https://github.com/feffi/ansible-macos-atom) [![GitHub forks](https://img.shields.io/github/forks/feffi/ansible-macos-atom.svg?style=social&label=Fork)](https://github.com/feffi/ansible-macos-atom) [![GitHub stars](https://img.shields.io/github/stars/feffi/ansible-macos-atom.svg?style=social&label=Star)](https://github.com/feffi/ansible-macos-atom) [![GitHub watchers](https://img.shields.io/github/watchers/feffi/ansible-macos-atom.svg?style=social&label=Watch)](https://github.com/feffi/ansible-macos-atom) [![Twitter Follow](https://img.shields.io/twitter/follow/feffi1.svg?style=social&label=Follow)](https://twitter.com/feffi1) [![License](http://img.shields.io/:license-mit-blue.svg)](https://github.com/feffi/ansible-macos-atom/blob/master/LICENSE)

## Requirements
- Ansible 2.3

### ansible.cfg
```
hash_behaviour = merge
```

## Install
Just add the role to your ``requirements.yml`` file:
```yaml
- src: https://github.com/feffi/ansible-macos-atom.git
  name: feffi.macos-atom
```

## Role Variables
All role based variables are listed below, along with default values:

```yaml
---
macos_atom:
  # Settings to be placed in the atom user preferences
  preferences:
    "*":
      core:
        disabledPackages: [
          ...
        ],
        projectHome: "/Users/fooo/"
        ...

  # Packages to be installed via PackageControl.io
  packages: [
    { name: "archive-view" },
    { name: "autocomplete-atom-api" },
    { name: "autocomplete-css", enabled: false },
    { name: "autocomplete-html", enabled: false },
    ...
  ]
```

## Dependencies
* [ansible-macos-homebrew](https://github.com/feffi/ansible-macos-homebrew)

## Example Playbook

```yaml
    - hosts: all
      vars:
        macos_atom:
          preferences:
            ...
          packages:
            ...
      roles:
        - { role: feffi.macos-atom }
```
Or with local parameters:

```yaml
    - hosts: all
      roles:
        - { role: feffi.macos-atom,
            macos_atom: {
              preferences: {
                ...
              },
              packages: [
                ...
              ]
            }
          }
```
