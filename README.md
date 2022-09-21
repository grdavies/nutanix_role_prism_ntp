Nutanix Role for Prism NTP server configuration
=========

This Ansible role sets the NTP server configuration for Prism Element and Prism Central.


Role Variables
--------------

| Variable                           | Required | Default | Choices                                                                         | Comments                                                                                                                                           |
|------------------------------------|----------|---------|---------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| validate_certs                     | no       | no      |                                                                                 | Whether to check if Prism UI certificates are valid.                                                                                               |
| prism_containers_remove_default    | no       | True    | True or False                                                                   | If set to True the default container will be removed if it exists.                                                                                 |
| prism_containers_list              | no       | []      |                                                                                 | List of containers. For container dict keys see table below.                                                                                       |


| Variable                           | Required | Default | Choices                                                                         | Comments                                                                                                                                           |
|------------------------------------|----------|---------|---------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| name                               | yes      |         |                                                                                 |                                                                                                                                                    |
| rf                                 | no       | 2       | 2 or 3                                                                          |                                                                                                                                                    |
| compression                        | no       | False   | True or False                                                                   |                                                                                                                                                    |
| compression_delay_in_secs          | no       | 0       |                                                                                 | 0 = inline compression.                                                                                                                            |
| dedupe_cache                       | no       | False   | True or False                                                                   |                                                                                                                                                    |
| dedupe_capacity                    | no       | False   | True or False                                                                   |                                                                                                                                                    |
| erasure_coding                     | no       | False   | True or False                                                                   |                                                                                                                                                    |


Dependencies
------------

- grdavies.nutanix_role_prism_init_api

Example Playbook
----------------

```
- hosts: localhost
  gather_facts: false
  roles:
    - role: ../..
  vars:
    prism_ip: 10.38.185.37
    prism_username: admin
    prism_password: nx2Tech165!
    prism_containers_list:
      - name: example
        rf: 2
        compression: True
        compression_delay_in_secs: 0
        dedupe_cache: False
        dedupe_capacity: False
        erasure_coding: False
      - name: example_2
        rf: 2
        compression: True
        compression_delay_in_secs: 60
        dedupe_cache: True
        dedupe_capacity: True
        erasure_coding: False
```


License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
