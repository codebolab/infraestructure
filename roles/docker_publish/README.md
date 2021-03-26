# Docker publish

Builds and publish an image into AWS ECR.

## Requirements

* 

## Example Playbook

    - hosts: dynamic
      ansible_user: ec2-user
      ansible_ssh_private_key_file: "{{ playbook_dir | dirname }}/private/{{ platform_name }}.pem"
      become: yes
      tasks:
        - include_role: 
            name: initializer_base
