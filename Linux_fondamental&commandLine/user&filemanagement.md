## User Management

- A user is identified by a Unique User ID UUID and it stored in __/etc/passwd__.

- Password are stored in hashed form in __/etc/shadow__.

- A user can be assigned a primary group and secondary groups.


## Creating and Managing Users

> - useradd: to create a new user.
> - usermod: to modify user properties.
> - userdel: to delete user and their home directory.

## Group Management

> - Groups allow us to assign permissions to multiple users.
> - Use __groupadd__, __usermod__ and groupdel for group management.

## Understanding File Permissions

> - Every file in linux has __read__(r) also __4__, __write__(w) also __2__ and __execute__(x) also __1__ permissions.

> - Permissions are assigned to three classes: Owner, group, and others.


## Changing Permissions and Ownership

> - Use __chmod__ to change file permissions.
> - __chown__ and __chgrp__ to change file and group ownership.

[Illustrative examples](/usermanagement.sh)