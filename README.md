# Nutanix Role for Prism NTP server configuration

This Ansible role sets the NTP server configuration for Prism Element and Prism Central.


## Role Variables

| Variable                 | Required | Default | Choices                                                                         | Comments                                                                                                                                           |
|--------------------------|----------|---------|---------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
| validate_certs           | no       | no      |                                                                                 | Whether to check if Prism UI certificates are valid.                                                                                               |
| prism_ntp_server_list    | yes      | []      |                                                                                 | Provide a list of NTP servers; ["0.pool.ntp.org", "1.pool.ntp.org", "2.pool.ntp.org", "3.pool.ntp.org"].                                                                                 |

## Dependencies

- grdavies.nutanix_role_prism_init_api


## Example Playbook

```
- hosts: localhost
  gather_facts: false
  roles:
    - role: grdavies.nutanix_role_prism_ntp
  vars:
    nutanix_host: 10.38.185.37
    nutanix_username: admin
    nutanix_password: nx2Tech165!
    prism_ntp_server_list:
      - 0.pool.ntp.org
      - 1.pool.ntp.org
      - 2.pool.ntp.org
      - 3.pool.ntp.org
```


## License

See LICENSE.md

## Author Information

Ross Davies
