# ansible-osx-computername
A Ansible role to setup a macOS hostname, smb name, netbios.

[![Build Status](https://travis-ci.org/feffi/ansible-osx-computername.svg?branch=master)](https://travis-ci.org/feffi/ansible-osx-computername)

## Requirements
- Ansible 2.3

### ansible.cfg
```
hash_behaviour = merge
```

## Install
Just add the role to your ``requirements.yml`` file:
```
- src: https://github.com/feffi/ansible-osx-computername.git
  name: feffi.osx-computername
```

## Role Variables
All role based variables are listed below, along with default values:

```
osx_computername:
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

    - hosts: all
      roles:
        - { role: feffi.osx-computername }

Or with local parameters:

    - hosts: all
      roles:
        - { role: feffi.osx-computername,
            osx_computername: {
              computer: "marvin",
              host: "marvin",
              localhost: "marvin",
              netbios: "marvin"
            }
          }
