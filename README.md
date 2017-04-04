# ansible-role-influxdb

This is an Ansible role for installing and configuring influxDB and the influxDB client packages on a rapsberry pi. InfluxDB will be configured to run on https and add an admin user. As this role is meant to be used within my my-pi-setups repository https://github.com/C3-TKO/my-pi-setups.


## Requirements

- Tested on Ansible 2.2.10
- Tested on Ubuntu 16.04 (xenial), but it should work on any modern Debian based system.

## Dependencies

This role expects that the host machine has already ufw setup

## Example playbook

To use this role, build a vars file (vars/influxdb.yml, for example) which you include in your playbook,
which contains something like the following:

    influx_admin_user:
     - admin
    influx_admin_pass:
     - changeme
    ssl_key_and_certificate_combined: |
    --- BEGIN PRIVATE KEY ---
    ...
    --- BEGIN CERTIFICATE ---

Next, you can include the role in your playbook:

    - hosts: all
      sudo: yes
      vars_files:
        - vars/influxdb.yml
      roles:
        - influxdb

## Licence

MIT

## Feedback? Found a bug? Requests?

Let me have it! https://github.com/C3-TKO/ansible-role-influxdb/issues
