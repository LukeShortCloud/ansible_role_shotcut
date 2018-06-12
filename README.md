# ansible-role-shotcut

A role to install, uninstall, or update the Shotcut video editor on Linux or mac OS.


## Requirements

None.


## Role Variables

Variables:

* install_state
    * absent = Uninstall Shotcut.
    * present = Install Shotcut if it is not present already.
    * latest = Update Shotcut.
* installation_dir = By default this is set to a user's home directory, as defined by the `$HOME` environment variable.
* shotcut_os = The operating system package to use. Currently only `linux` is supported.
* shotcut_version_full = The full 6-digit Shotcut version number. This should be in a time format similar to ISO.
    * Releases: https://github.com/mltframework/shotcut/releases


## Dependencies

None.


## Example Playbooks

Playbook file (shotcut.yml):

```
---
- hosts: localhost
  roles:
    - ansible-role-shotcut
```

Install Shotcut:

```
$ ansible-playbook shotcut.yml
```

Install a specific version of Shotcut:

```
$ ansible-playbook --extra-vars "shotcut_version_full=180508" shotcut.yml
```

Update Shotcut:

```
$ ansible-playbook --extra-vars "install_state=latest" shotcut.yml
```

Uninstall Shotcut:

```
$ ansible-playbook --extra-vars "install_state=absent" shotcut.yml
```

## License

GPLv3
