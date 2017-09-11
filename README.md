# ansible-macos-computername
A Ansible role to setup a macOS hostname, smb name, netbios.

[![Build Status](https://travis-ci.org/feffi/ansible-macos-computername.svg?branch=master)](https://travis-ci.org/feffi/ansible-macos-computername)

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
  computer: ""

  # The macOS hostname associated with hostname(1) and gethostname(3).
  host: ""

  # The macOS hostname used for Bonjour-aware services on the local network.
  localhost: ""

  # The hosts Netbios advertising name.
  netbios: ""
```

## Dependencies
None.

## Example Playbook

```yaml
    - hosts: all
      roles:
        - { role: feffi.macos-computername }

Or with local parameters:

    - hosts: all
      roles:
        - { role: feffi.macos-computername,
            macos_computername: {
              computer: "marvin",
              host: "marvin",
              localhost: "marvin",
              netbios: "marvin"
            }
          }
```
