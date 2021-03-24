# infraestructure

A set a playbooks to create clusters and turn up or turn down services.

## Configurations

Create an environment:

    $ conda create --name devops python=3.6

Install required packages:

    $ pip install -r requirements.txt

Create and edit credentials file:

    $ cp playbooks/vars/credentials.example.yml playbooks/vars/credentials.yml

Fill credentials file with real values:

    ---
    aws_region: us-east-1
    aws_access_key: access key here
    aws_secret_key: secret key here

Encrypt credentials file:

    $ ansible-vault encrypt playbooks/vars/credentials.yml

Edit platform vars:

    ---
    # Service
    platform_name: example 
    service_id: api
    service_port: 80

    # AWS
    s3_bucket: examplelake

    # DNS
    zone: example.com

## Playbooks

* `cluster_public.yml` Creates a VPC, public subnets, internet gateway, security groups and a head instance.
