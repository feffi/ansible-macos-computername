# ansible-macos-computername
A Ansible role to setup a macOS hostname, smb name, netbios.

[![Build Status](https://img.shields.io/travis/feffi/ansible-macos-computername.svg)](https://travis-ci.org/feffi/ansible-macos-computername) [![Github All Releases](https://img.shields.io/github/downloads/feffi/ansible-macos-computername/total.svg)](https://github.com/feffi/ansible-macos-computername) [![GitHub forks](https://img.shields.io/github/forks/feffi/ansible-macos-computername.svg?style=social&label=Fork)](https://github.com/feffi/ansible-macos-computername) [![GitHub stars](https://img.shields.io/github/stars/feffi/ansible-macos-computername.svg?style=social&label=Star)](https://github.com/feffi/ansible-macos-computername) [![GitHub watchers](https://img.shields.io/github/watchers/feffi/ansible-macos-computername.svg?style=social&label=Watch)](https://github.com/feffi/ansible-macos-computername) [![Twitter Follow](https://img.shields.io/twitter/follow/feffi1.svg?style=social&label=Follow)](https://twitter.com/feffi1) [![License](http://img.shields.io/:license-mit-blue.svg)](https://github.com/feffi/ansible-macos-computername/blob/master/LICENSE)

## Requirements
- Ansible 2.3

### ansible.cfg
```
hash_behaviour = merge
```

## Install
Just add the role to your ``requirements.yml`` file:
```yaml
- src: https://github.com/feffi/ansible-macos-computername.git
  name: feffi.macos-computername
```

## Role Variables
All role based variables are listed below, along with default values:

```yaml
macos_computername:
  # The macOS "user-friendly name for the system", appears mainly in GUI.
  ComputerName: ""

  # The macOS hostname associated with hostname(1) and gethostname(3).
  HostName: ""

  # The macOS hostname used for Bonjour-aware services on the local network.
  LocalHostName: ""

  # The hosts Netbios advertising name.
  NetBIOSName: ""
```

## Dependencies
None.

## Example Playbook

```yaml
    - hosts: all
      vars:
        macos_computername:
          ComputerName: "tardis"
          HostName: "tardis"
          LocalHostName: "tardis"
          NetBIOSName: "tardis"
      roles:
        - { role: feffi.macos-computername }
```
Or with local parameters:

```yaml
    - hosts: all
      roles:
        - { role: feffi.macos-computername,
            macos_computername: {
              ComputerName: "marvin",
              HostName: "marvin",
              LocalHostName: "marvin",
              NetBIOSName: "marvin"
            }
          }
```
