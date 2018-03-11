# Ansible Role: Linux Customization
[![Build Status](https://travis-ci.org/brentwg/ansible-role-linux-customization.svg?branch=master)](https://travis-ci.org/brentwg/ansible-role-linux-customization)

These are minimal configuration changes that are performed after every new Linux workstation installation. This role was created for the following Ansible Playbook: [Linux DevOps Workstation](https://github.com/brentwg/ansible-linux-workstation).

## Requirements  

None.  

## Objectives
1. Install additional software packages (and groups - RedHat)  
1. Disable SELinux (RedHat)  
1. Enable NOPASSWD `sudo`  
1. Install OpenSSH Server  
    - Enable the service to start on boot  
    - Disable root login  
    - Disable GSS API authentication  

## Role Variables  

You can override the following variables:  
```
additional_packages: []
```
I provided a default listing of packages that I like to install after first boot.  
```
additional_groups: []
```
I also provided a listing of default package groups (however, this is broken on CentOS 7, so I just use it for Fedora)

## Dependencies

None

## Sample Playbook
```
- hosts: all
  
  roles:
    - brentwg.linux-customization
```
