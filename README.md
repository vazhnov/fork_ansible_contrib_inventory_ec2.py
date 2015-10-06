## Intro

Because of too much unwanted pulls to original Ansible dynamic inventory script `contrib/inventory/ec2.py`, created fork. Here you can push new features and style fixes.

## Difference

### tag_destination_variable

You can use list of tags, separated by commas.
Example usage:
```ini
tag_destination_variable = Name,Domain
```
If ec2 tags is «Name=srv01», «Domain=example.com.», then resulted hostname is «srv01.example.com», without any last dot (cutted by code).

### vpc_subnets

In dynamic inventory added dictionary «vpc_subnets» with key=subnet id and value=VPC information, so now you can easy find VPC id by subnet id.
Also added lists «subnet in vpc».
You can disable this by configuration option:
```ini
vpc_subnets = False
```

## ToDo

* Add groups by state (running, stopped);

## P.S.

I'm not Python/Ansible developer, just a system administrator.
