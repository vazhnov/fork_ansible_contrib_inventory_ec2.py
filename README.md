## Intro
Because of too much unwanted pulls to original Ansible contrib/inventory/ec2.py, created fork. Here you can push new features and style fixes.

## Difference
### tag_destination_variable
You can use list of tags, separated by commas.
Example usage:
```
#!ini

tag_destination_variable = Name,Domain
```
If ec2 tags is «Name=srv01», «Domain=example.com.», then resulted hostname is «srv01.example.com», without any last dot (cutted by code).

## ToDo
* Add groups by state (running, stopped);

## P.S.
I'm not Python/Ansible developer, just a system administrator.
