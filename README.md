[![Build Status](https://travis-ci.org/sperreault/ansible-net-powerdns-recursor.svg)](https://travis-ci.org/sperreault/ansible-net-powerdns-recursor)

net-djbdns
=========

Ansible Role to configure powerdns-recursor from pkgsrc

Requirements
------------

- Hosts requires pkgsrc's pkgin
- Hosts should be bootstrapped for ansible usage (have python,...)
- Root privileges, eg `become: yes`

Role Variables
--------------

| Variable | Description | Default value |
|----------|-------------|---------------|
| `net_powerdns_recursor_config_file_src` | Local location of recursor.conf.j2 | `"recursor.conf.j2"` | 
| `net_powerdns_recursor_config_file_dest` | Remote location of the configuration file | `"/opt/local/etc/recursor.conf"` | 
| `net_powerdns_recursor_config_local_address` | Where do we listen | `"0.0.0.0"` | 
| `net_powerdns_recursor_config_local_port` | What port should we listen on | `"53"` | 
| `net_powerdns_recursor_username` | Username of the running process | `"root"` | 
| `net_powerdns_recursor_groupname` | Group of the running process | `"root"` | 
| `net_powerdns_recursor_service_name` | Service name | `"pkgsrc/pdns-recursor"` | 
| `net_powerdns_recursor_root_hints_url` | Hints file to use (check your configuration) | `"ftp://ftp.internic.net/domain/named.cache"` | 
| `net_powerdns_recursor_root_hints_file` | Local copy of the hints file  | `"/var/cache/root.hints"` | 

Dependencies
------------

None

Example Playbook
----------------


    - hosts: servers
      roles:
         - { role: sperreault.net-powerdns-recursor }

License
-------

BSD

Author Information
------------------

Sebastien Perreault <sperreault@alesium.net>
