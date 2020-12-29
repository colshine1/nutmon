nutmon
=========

Network UPS Tool Automation Installation on Raspberry Pi

Requirements
------------


Role Variables
--------------

```
nutmon_ubuntu_package_list:
  - nut

nutmon_config_files_dir: /etc/nut

nutmon_config_file:
  - ups.conf
  - nut.conf
  - upsd.users
  - upsd.conf
  - upsmon.conf

ups:
  name: apc_smt_1500
  driver: usbhid-ups
  port: auto
  desc: "APC Smart-UPS 1500IC"
  mode: netserver|netclient|standalone

synology_client: false #  set this to true if you want to connect a Synology Diskstation as a client to your nut server. This will overrides the ups.name variable to ups in the upsmon.conf, ups.conf and upsd.users. It will also add a set of default credentials for the monuser in upsd.users to allow connections from Synology Diskstation.

# Passwords
_vault_admin_password:
_vault_admin_upsmon_local:
_vault_admin_upsmon_remote:
_vault_admin_monuser: # This value is only used if synology client is set to false.
```

Dependencies
------------


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: nutmon

License
-------

GNU GPLv3

Author Information
------------------

Irum Malik
