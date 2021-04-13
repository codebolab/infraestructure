# SPA s3 deploy

Deploy a frontend application into s3.

## Role Variables

| Variable          | Type    | Choices  | Default      | Comment                                |
|-------------------|---------|----------|--------------|----------------------------------------|
| `bucket_name`     | string  |          |              | Bucket name to deploy                  |
| `fileroot`        | string  |          |              | Path to static files to deploy into s3 |

## Example Playbook

    - hosts: dynamic
      ansible_user: ec2-user
      become: yes
      tasks:
        - include_role: 
            name: codebolab.devops.spa_s3_deploy
          vars:
            bucket: www.example.com
            fileroot: "{{ playbook_dir | dirname }}"

