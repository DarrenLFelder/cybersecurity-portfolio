# Linux File Permissions and Authorization

## Project Overview

This project demonstrates the use of Linux commands to examine and modify file and directory permissions based on organizational authorization requirements.

The objective was to identify excessive permissions, remove unauthorized access, configure permissions for a hidden archived file, restrict access to a directory, and verify the resulting permissions.

## Environment

- Linux
- Bash shell
- Debian-based virtual machine

## Commands Used

- `pwd`
- `ls`
- `ls -la`
- `chmod`

## Permission Analysis

I used `ls -la` to examine detailed permissions for files and directories, including hidden files.

Linux permissions were evaluated across three authorization categories:

- User
- Group
- Other

The permission characters `r`, `w`, and `x` represent read, write, and execute permissions.

## File Permission Remediation

### project_k.txt

The file allowed others to write to it:

`-rw-rw-rw-`

The organization's policy did not allow others to have write access, so I removed that permission:

`chmod o-w project_k.txt`

Result:

`-rw-rw-r--`

### Hidden File: .project_x.txt

The archived hidden file needed to allow the user and group to read the file while preventing write access.

I modified the permissions using:

`chmod u-w,g-w,g+r .project_x.txt`

Result:

`-r--r-----`

This allows the user and group to read the file while preventing write access.

### drafts Directory

Only the owner, `researcher2`, was authorized to access the `drafts` directory.

I removed execute permission from the group:

`chmod g-x drafts`

Result:

`drwx------`

This leaves the owner with read, write, and execute permissions while removing access for the group and others.

## Verification

After modifying the permissions, I used:

`ls -la`

to verify that the authorization changes had been successfully applied.

## Skills Demonstrated

- Linux command-line administration
- File and directory permissions
- Authorization management
- Principle of least privilege
- Bash shell navigation
- Hidden file identification
- Permission analysis
- `chmod` permission modification
- Security control verification

## Project Files

- Completed Linux file permissions analysis
- Terminal evidence showing permission changes and verification

## Project Context

This project was completed in a simulated Linux security environment. The permission analysis, authorization decisions, Linux commands, remediation actions, and verification demonstrate my hands-on understanding of Linux file-system access controls.
