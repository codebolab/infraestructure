# Initializer base

Install development tools, python libraries and configure EPEL repo into a AWS centos server.

## Requirements

This role was developed to initialize the basic AWS linux server with essential development tools.

## Example Playbook

    - hosts: dynamic
      ansible_user: ec2-user
      ansible_ssh_private_key_file: "{{ playbook_dir | dirname }}/private/{{ platform_name }}.pem"
      become: yes
      tasks:
        - include_role: 
            name: initializer_base
