---
title: "Modifying File Access Modes In Unix-based Systems"
seoTitle: "Unix File Permissions: Master chmod for Access Control"
seoDescription: "Learn to modify file access modes with symbolic and numeric methods, ensuring precise access control for owners, groups, and others in shared environments."
datePublished: Sun Nov 12 2023 14:01:37 GMT+0000 (Coordinated Universal Time)
cuid: clovjnt8h00070ajufxji1fpd
slug: modifying-file-access-modes-in-unix-based-systems
cover: https://cdn.hashnode.com/res/hashnode/image/stock/unsplash/4Mw7nkQDByk/upload/435d85ab848c5484eb01bccc56692388.jpeg
tags: terminal, command-line, chmod, file-permission

---

# Introduction

When multiple users share a computer system (e.g. at work), they share access to directories and files. What if a user on a shared system creates a file and wants only select users to have access? In Unix-based systems, changing the file access mode is the way to achieve this.

Only the owner (i.e. the creator) of a file can change the file access mode. The file owner can command that a group of users have access to the file while others do not. Therefore, there are 3 classes of file users: the owner, group, and others.

Users have more than one way of accessing files. So when file owners grant users access to their files, they also have to choose what kind of access they permit. They may permit users read, write, and/or execute access.

# Prerequisite

* Familiarity with the command prompt or termina
    
* Understanding of Basic Unix System Operations
    

# Change File Access Modes

Unix-based systems provide a system call known as the *chmod* command. This command is used by file owners to ‘change mode’ or change how users are permitted to interact with their files. This includes changing the read-write-execute permissions of the file owner, group, and others.

The *chmod* command takes 2 mandatory arguments: MODE, and FILE.

```bash
chmod MODE FILE
```

MODE represents permissive changes to make to FILE, and can either be symbolic or numeric.

## Symbolic Mode

The symbolic mode represents file mode changes with symbolic characters.

```bash
chmod [ users ] [ [ - + = ] [ perms ] ]  FILE
```

These symbols include:

* User symbols: **u** for owner, **g** for group, **o** for others, and **a** for all users.
    
* Permission symbols: **r** for read, **w** for write, **x** for execute, etc.
    
* Operational symbols: **\-** for remove, **+** for add, and **\=** for replace
    

One or more of the symbols in ***ugo*** or just ***a*** can represent the users who are about to gain or lose permissions, while zero or more of the symbols in ***rwx*** can represent the permissions.

Permissions must be prefixed with an operational symbol. The operational symbols tell *chmod* what to change about the users’ permissions.

```bash
# Revoke group permission to write FILE
chmod g-w FILE

# Grant owner permission to write and execute FILE
chmod u+wx FILE

# Grant others permission to read FILE 
# and revoke any other existing permission
chmod o=r FILE
```

Where zero permissions are specified, *chmod* applies the default permissions (for the FILE type and location) to the user.

## Numeric Mode

The numeric mode uses one or more clusters of octal numbers ( i.e. numbers in base 8) to represent permissions.

```bash
chmod OCTAL-MODE FILE
```

Precedence takes place from the right starting with others, followed by group, and followed by owner. This has the following positional effect:

* *Others* can be represented with *one* or more digits (e.g 7, 07, 007)
    
* *Group* requires a minimum of *two* or more digits (e.g 70, 070)
    
* *Owner* requires a minimum of *three* digits (e.g. 700)
    

This means that any octal mode less than 3-digit long (e.g. 77) would omit some users. However, all omissions are automatically replaced with 0s. Consequentially, a zero in numeric mode would withdraw all permissions from the class of users it is positioned at.

```bash
# Revoke all users permissions to read, write, and execute FILE
chmod 0 FILE
```

Revoking all 3 permissions from the file owner is not a likely call. Since the numeric mode requires all users’ permissions described when using it, using up to 3 digits might be the ideal way to go.

Other octal numbers also mean something in the numeric mode.

| **Octal** | **Permissions** |
| --- | --- |
| **To grant:** | **To revoke:** |
| 0 |  |
| 1 | execute |
| 2 | write |
| 3 | write and execute |
| 4 | read |
| 5 | read and execute |
| 6 | read and write |
| 7 | read, write, and execute |

As each of these numbers grants one or more permissions to users, they also revoke all permissions they do not grant. This is similar to the equal-to `=` operator in the symbolic mode.

The numeric mode is great for changing all file permissions at once. It’s also got elegant syntax.

```bash
# Grant owner permission to read, write, and execute FILE
chmod 755 FILE

# Grant owner permission to read, write, and execute FILE
chmod 710 FILE

# Grant owner permission to read and write FILE
chmod 644 FILE
```

# Exceptions

While the *chmod* command changes the permissions of files, it does not change the permissions of symbolic links. Instead, it changes the permissions of the pointed-to file.

# Conclusion

This resource does not exhaust the uses of the *chmod* command. The command modifies attributes of the file access mode beyond the read, write, and execute permissions. It also modifies the access modes of directories.

Both the *chmod* system call and the file access modes are essential utilities in Unix-based systems. Their essence in shared computer systems, as discussed in this resource and beyond, makes them invaluable assets to computer users and administrators.

# References

GNU. (2023). chmod(1) - Linux man page. Retrieved October 26, 2023, from [https://linux.die.net/man/1/chmod](https://linux.die.net/man/1/chmod)