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
* shotcut_archive = The name of the archive that will be downloaded.
* shotcut_url = The full URL link to download the Shotcut binaries for Linux.

The information for different versions to use for `shotcut_archive` and `shotcut_url` can be found here: https://github.com/mltframework/shotcut/releases


## Dependencies

None.


## Example Playbooks

Install Shotcut:

```
---
- hosts: localhost
  vars:
    install_state: latest
  roles:
    - ansible-role-shotcut
```

Uninstall Shotcut:

```
---
- hosts: localhost
  vars:
    install_state: absent
  roles:
    - ansible-role-shotcut
```

## License

GPLv3
