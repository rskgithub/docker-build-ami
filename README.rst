docker-build-ami
================

Build Amazon EC2 AMI image using a Dockerfile

Limitations
===========
Only supports instructions ENV, RUN, COPY and ADD, other instructions will just be ignored.

Configuration
=============

There is a separate config file for the script in either "/etc/docker-build-ami.conf" or "~/.docker-build-ami.conf".

.. code-block::

    # [main]

    # Temporary directory
    # tmp_dir = /tmp

    # Name tag for host building AMI image
    # host_tag = 'docker-build-ami'

    # Region
    # region = eu-west-1

    # Instance type
    # instance_type = m3.medium

    # Subnet ID
    # subnet_id = subnet-123abc45

    # Security Groups
    # security_group_ids = ["sg-1234", "sg-23456"]

    # Host Tags - additional tags to add to EC2 host
    # host_tags = [{"Key": "foo", "Value": "bar"}]

    # AWS access key id
    # aws_access_key_id = DFSDF3HGDF4SDSD1DDFF

    # AWS secret access key
    # aws_secret_access_key = 3riljdsf5SDFSDvsdfds452sdSDFDfsdf44SDFdRA

    # Base image from which the output image is built
    # image_id = ami-0df67e2624dedbae1

    # EC2 user used to build instances (usually AMI dependent)
    # image_user = ubuntu

    # The AMI Name of the output image
    # image_name = ubuntu-test

    # Image Tags - tags to add to AMI
    # image_tags = [{"Key": "foo", "Value": "bar"}]


Usage
=====

.. code-block::

    usage: docker-build-ami [-h] [-c CONFIG] [-d] [-r] [-t] [-s] [-n] [-i] [-u]

    optional arguments:
      -h, --help            show this help message and exit
      -c CONFIG, --config CONFIG
                        Configuration file
      -d, --debug           Print debug info
      -r, --region          AWS region
      -t, --instance-type   EC2 instance type
      -s, --subnet-id       AWS subnet id
      -n, --image-name      Target AMI image name
      -i, --image-id        Source AMI image ID
      -u, --image-user      AMI image user

