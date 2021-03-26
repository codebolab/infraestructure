# Initializer nginx

Install and configure NGinx server

## Requirements

Works on AWS CentOS linux server

## Example Playbook

    - hosts: dynamic
      ansible_user: ec2-user
      become: yes
      tasks:
        - include_role:
            name: initializer_nginx
