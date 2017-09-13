# ansible_role_os_server

This is an Ansible role. This role manage instance on OpenStack environment.

## Processing
This role executes the following settings.

* create or delete instance

## Prerequirement
Before using this role, install shade which is a python module to the ansible server.

## Usage
1. describe the names of instances into the inventory. Example of the inventory is as follows;
```
os_instance01
os_instance02
os_instance03
```
2. create the host_vars file whose name is the same of instance name (e.g., os_instance01.yml)

3. run the playbook in which this role is described 

## Support OS

| OS | version |
|----|---------|
|CentOS|7|

## Role variables
```
os_server:
  openrc:                 
    domain: default                                               # domain name
    project: bbrfkr                                               # project name
    user: bbrfkr                                                  # user name
    password: password                                            # password
    keystone_endpoint: "http://keystone.bbrfkr.mydns.jp:5000/v3"  # endpoint of Identity Service
  image: CentOS7                                                  # image of instance
  az: nova                                                        # availability zone
  flavor: m1.small                                                # flavor of instance
  network: network01                                              # network to which instance belongs
  attach_floating_ip: no                                          # whether attach floating ip to instance
  security_groups:                                                # security groups
    - default
    - http-https
  key_pair: key01                                                 # key pair of instance
  state: present                                                  # state (present or absent)
```

## Dependencies
None

## License
MIT

## Author
Name: bbrfkr  
MAIL: bbrfkr@gmail.com

