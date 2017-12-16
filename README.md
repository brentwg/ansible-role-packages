# Ansible Role: Packages

[![Build Status](https://travis-ci.org/brentwg/ansible-role-packages.svg?branch=master)](https://travis-ci.org/brentwg/ansible-role-packages)

A simple Ansible role used to install software updates and install additional (specified) packages.  

(Mostly this is a proof-of-concept so that I might force entry into the hallowed arena of automated build testing on GitHub...)  

## Requirements  
None.  

## Role Variables  
Available variables, as well as their default values, are listed below (See `defaults/main.yml` and distro-specific files in `vars/*.yml`):  
```
install_package_updates: true
```  
Set `install_package_updates` to `true` to enable the automated installation of software package updates. Set it to `false` to disable updates.  

```
add_packages: []
remove_packages: []
```  
Both `add_packages` and `remove_packages` expect to receive a list of package names that are specific to whichever Linux distribution you are running. For testing purposes, I added an appropriate variant of VIM (full version).  

## Dependencies  
None.  

## Example Playbook
```
- hosts: all

  vars:
    install_package_updates: false
    add_packages:
    - vim-enhanced
    
  roles:
    - path/to/ansible-role-packages
```
