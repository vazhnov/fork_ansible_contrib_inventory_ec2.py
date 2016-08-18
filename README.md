## Intro

Because of too much unwanted pulls to original Ansible dynamic inventory script `contrib/inventory/ec2.py`, created fork. Here you can push new features and style fixes.

## Difference

### tag_destination_variable

This option has been deleted, because of [new options in upstream](https://github.com/ansible/ansible/pull/10385):
* `destination_format`
* `destination_format_tags`

### vpc_subnets

In dynamic inventory added dictionary «vpc_subnets» with key=subnet id and value=VPC information, so now you can easy find VPC id by subnet id.
Also added lists «subnet in vpc».
You can disable this by configuration option:
```ini
vpc_subnets = False
```
Will be replaced by module [ec2_vpc_subnet_facts](https://docs.ansible.com/ansible/ec2_vpc_subnet_facts_module.html) in Ansible v2.1.

### Set variables ansible_host and ansible_ssh_host

Variables `ansible_ssh_host` and `ansible_host` (for compatibility with Ansible v2) can be appended in every hostvars (copied from `ec2_ip_address`), so you can see names from EC2 tags, but connect to ip addresses.
You can enable this by configuration option:
```ini
add_var_ansible_host = True
```

## ToDo

* Add groups by state (running, stopped);

## Another forks:

* [ansible-ec2-inventory](https://pypi.python.org/pypi/ansible-ec2-inventory) — you can install from pip;

## P.S.

I'm not Python/Ansible developer, just a system administrator.
