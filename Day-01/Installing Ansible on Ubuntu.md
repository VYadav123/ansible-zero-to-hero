# Installing Ansible on Ubuntu
This document provides a step-by-step guide to installing Ansible on an Ubuntu system.

Prerequisites
An Ubuntu machine with sudo privileges.

An active internet connection.

Installation Steps
Ansible can be installed from the Ubuntu repositories or using pip, the Python package installer. The recommended method for Ubuntu is to use the official PPA (Personal Package Archive).

Method 1: Using the Ansible PPA (Recommended)

Update Package Lists:

Open a terminal and update the system's package lists:

sudo apt update

This ensures you have the latest package information.

Install software-properties-common:

Install this package, which provides utilities for managing software repositories:

sudo apt install software-properties-common

Add the Ansible PPA:

Add the official Ansible PPA to your system's software sources:

sudo add-apt-repository --yes --update ppa:ansible/ansible

--yes: Automatically answer "yes" to any prompts during the PPA addition.

--update: Refresh the package lists after adding the PPA.

Install Ansible:

Install the Ansible package:

sudo apt install ansible

Verify Installation:

Check that Ansible is installed correctly by displaying its version:

ansible --version

Method 2: Using pip (Alternative)

Install pip and Python Development Tools:

Install pip, the Python package manager, and other necessary development tools:

sudo apt install python3-pip python3-dev

Install libffi-dev and libssl-dev:

Install these libraries, which are often required for Ansible's dependencies:

sudo apt install libffi-dev libssl-dev

Install Ansible with pip:

Install Ansible using pip:

pip3 install ansible

Verify Installation:

Verify the installation:

ansible --version

Configuration
After installation, you'll need to configure Ansible. The primary configuration file is /etc/ansible/ansible.cfg. You'll also need to set up your inventory file, which lists the hosts you want to manage.

Inventory File:

The default inventory file is located at /etc/ansible/hosts. You can create or modify this file to define your managed hosts.  A simple inventory file might look like this:

[my_hosts]
host1.example.com
host2.example.com

SSH Key Setup

For passwordless authentication, you'll need to set up SSH keys.  This involves generating a key pair on your control machine and copying the public key to the authorized_keys file on your managed hosts.

Getting Started
Once Ansible is installed and configured, you can start using it to automate tasks.  Here are some basic Ansible commands:

ansible all -m ping:  Tests connectivity to all hosts defined in your inventory file.

ansible <hostname/group> -m <module_name> -a "<module_arguments>":  Executes a specific Ansible module on the specified hosts.
