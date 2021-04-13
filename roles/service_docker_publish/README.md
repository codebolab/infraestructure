# Docker publish

Builds and publish an image into AWS ECR.

## Requirements

* `docker` service
* docker python library `pip install docker`

## Role Variables

| Variable          | Type    | Choices  | Default                 | Comment                                             |
|-------------------|---------|----------|-------------------------|-----------------------------------------------------|
| `aws_region`      | string  |          |                         | AWS region to publish the image                     |
| `platform_name`   | string  |          |                         | Name (identifier) of the project                    |
| `dockerfile_path` | string  |          | `dirname(playbook_dir)` | Directory to find the Docker file                   |
| `tag_name`        | string  |          |                         | Docker tag for the new image                        |
| `nocache`         | string  | yes,no   | no                      | Flag to prevent using caching on building the image |


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
