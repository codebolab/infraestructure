# NGinx site

Adds a configuration to proxy pass to a service

## Requirements

* `nginx` service

## Role Variables

| Variable          | Type    | Choices  | Default                 | Comment                                                 |
|-------------------|---------|----------|-------------------------|---------------------------------------------------------|
| `host_target`     | string  |          | 127.0.0.1               | Host to point                                           |
| `port_target`     | string  |          | 8000                    | Port to point                                           |
| `hostname`        | string  |          |                         | Hostname to listen requests.                            |
| `static_dir`      | string  |          |                         | Directory where static files and media files are stored |

## Example Playbook

    - hosts: dynamic
      ansible_user: ec2-user
      ansible_ssh_private_key_file: "{{ playbook_dir | dirname }}/private/{{ platform_name }}.pem"
      become: yes
      vars:
        platform_name: example
      tasks:
        - include_role: 
            name: docker_publish
          vars:
            dockerfile_path: "{{ playbook_dir | dirname }}"
