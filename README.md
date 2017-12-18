# Ansible Role: Packages

[![Build Status](https://travis-ci.org/brentwg/ansible-role-packages.svg?branch=master)](https://travis-ci.org/brentwg/ansible-role-packages)

A simple Ansible role used to install, remove, and update software packages.  

(Mostly this is a proof-of-concept so that I might force entry into the hallowed arena of automated build testing on GitHub...)  

## Requirements  
None.  

## Role Variables  
Available variables, as well as their default values, are listed below (See `defaults/main.yml` and distro-specific files in `vars/*.yml`):  
```
install_all_package_updates: true
```  
Set `install_all_package_updates` to `true` to enable the automated installation of all software package updates. Set it to `false` to disable all updates.  

```
install_packages: []
remove_packages: []
update_packages: []
```  
`install_packages`, `remove_packages`, and `update_packages` expect to receive a list of package names that are specific to whichever Linux distribution you are running. For testing purposes, I added an appropriate variant of VIM (full version).  

**NOTE**: If you've already set `install_all_package_updates` to `true`, then there is naturally no requirement to redundantly list specified packages; however, program logic would still allow this (since there is *probably* no harm done).  
## Dependencies  
None.  

## Example Playbook
```
- hosts: all

  vars:
    install_all_package_updates: true
    add_packages:
    - vim-enhanced
    
  roles:
    - brentwg.packages
```
