# DevOps4.3

This vagrant will install 2 Ubuntu 18.04 machines.
It will add some default users, groups and directory's.
This Vagrant is to practice system hardening..
This repository is intended for educational purpose only.


## Prerequisites

Works on Windows 10 and tested on macOS (macOS needs the Virtualbox extension pack).

Software needed:
* Virtualbox 5.0 or higher
* Git bash for Windows
* Vagrant 2.2.6 or higher


## Demo installation && use Vagrant

Youtube: https://youtu.be/KABnIuaA8SM


## Installation

* Install Virtualbox: https://www.virtualbox.org/wiki/Downloads
* Install Git bash for Windows: https://gitforwindows.org/
* Install Vagrant for Windows: https://www.vagrantup.com/downloads.html

## Run this Vagrant VM
Open **Git Bash** in Windows
```
cd Documents
mkdir vagrant && cd vagrant
git clone https://github.com/borahuho/DevOps4.3
cd DevOps4.3
vagrant up
vagrant ssh web1 of vagrant ssh web2
```
## Mission

Read your mission

## Network
Vagrant VM will be set up with 2 network adapters
```
Web1
Nat : DHCP
Localhost : 192.168.10.243

Web2
Nat : DHCP
Localhost : 192.168.10.244
```
## Vagrant commands
Make a new VM with Vagrant
```
vagrant up
```
Pause a VM
```
vagrant suspend
```
Restart a paused VM
```
vagrant resume
```
Stop and shutdown a VM
```
vagrant halt
```
Remove a VM
```
vagrant destroy
```
ssh in to the VM
```
vagrant ssh web1
vagrant ssh web2
```

