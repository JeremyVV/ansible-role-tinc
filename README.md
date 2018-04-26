## ansible-role-tinc [![Build Status](https://api.travis-ci.org/JeremyVV/ansible-role-tinc.svg?branch=master)](https://travis-ci.org/JeremyVV/ansible-role-tinc)

---

Ansible role which installs and configures tinc (as well as epel repo and rsync as dependencies) on CentOS.


#### Installation

This has been tested on Ansible 2.4.0 and higher.

To install:

```
git clone https://github.com/JeremyVV/ansible-tinc.git

```


#### Dependencies

- RHEL 7/CentOS 7
- rsycn
- epel repo


#### Compatibility matrix
- CentOS 7.x :heavy_check_mark:
- CentOS 6.x :grey_question:
- Ubuntu 16.04 :interrobang:
- Ubuntu 14.04 :interrobang:
- Debian 9.x :interrobang:
- Debian 8.x :interrobang:
- Fedora latest :grey_question:

- :heavy_check_mark: - tested, works fine
- :grey_question: - will work in the future (help out if you can)
- :interrobang: - maybe works, not tested
- :x: - doesn't work


#### Variables

```yaml
# Basic settings
tinc_netname: my.vpn
tinc_physical_ip: "{{ ansible_eth1.ipv4.address }}"
tinc_vpn_interface: tun0
tinc_vpn_netmask: 255.255.255.0
tinc_vpn_network: 10.0.0.0
tinc_vpn_cidr: 24
tinc_mode: switch


# host_vars
tinc_vpn_ip: 10.0.0.5
tinc_host: 167.160.185.238
```

#### Example Playbook

tinc.yml playbook

    - hosts: tinc
      roles:
         - ansible-tinc

Here is an example host_var file
```yaml
vpn_ip: 10.0.0.5
tinc_host: 167.160.185.238
```

#### Testing

If you are contributing ensure your change is covered in the tests found in [.travis.yml](./.travis.yml)


#### License

Licensed under the MIT License. See the [LICENSE](./LICENSE) file for details.


#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/JeremyVV/ansible-tinc/issues)!
