# ansible-role-usbip

This role installs usbip and is able to configure binds as systemd service.
Attaching devices with a systemd service should also work but maybe not too well.
It is written and tested against Ubuntu 18.04/20.04 and should also work with Debian.

## Examples
simple example with default vars:
```
- name: install usbip
  hosts: all
  tags:
    - usbip
  roles:
    - ansible-role-usbip
```
a more practical server example:

```
- name: install usbip
  hosts: all
  tags:
    - usbip
  roles:
    - ansible-role-usbip
  vars:
    - usbip_install_server: true
    - usbip_bind_devices: ["3-6"]
```
a more practical client example:

```
- name: install usbip
  hosts: all
  tags:
    - usbip
  roles:
    - ansible-role-usbip
  vars:
    - usbip_attach_devices:
      - remote_host: localhost
        bus_id: "3-6"
        name: secu
```
