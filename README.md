# aws-switch-off-environment

[![Build Status](https://travis-ci.org/kgogolek/aws-switch-off-environment.svg?branch=master)](https://travis-ci.org/kgogolek/aws-switch-off-environment)

Ansible playbook to switch whole environment on/off
It will do the following:
* Start / Stop Elasticache servers
* Start / Stop EC2 Instances matching a certain tag
* Scale down ASG groups defined

## Requirements

Ansible 2.x

## Playbook variables

All of the variables are set in ```vars/default.yml```

|Variable|Description|Default|
|---|---|---|
|```environment_base_domain```|Base domain on which elasticache servers will reside|test.com|
|```environment_region```|Region in which script is run|eu-west-1|
|```environment_tag```|EC2 Instance Tag Key|Environment|
|```environment_cache_servers```|List of elastcache servers to start, with parameters|{}|
|```environment_asg_groups```|List of ASG groups to scale up/down|{}|

## Example Run

    ansible-playbook -i ec2.py stop_environment.yml -e "env=staging"

## License

MIT / BSD

## Author Information

Kasia Gogolek <kasia@gogolek.co.uk>