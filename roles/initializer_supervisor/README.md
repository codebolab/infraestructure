# Initializer Superivosrd

Install and configure Supervisor

## Requirements

Works on AWS CentOS linux server

## Example Playbook

    - hosts: dynamic
      ansible_user: ec2-user
      become: yes
      tasks:
        - include_role:
            name: initializer_supervisor
