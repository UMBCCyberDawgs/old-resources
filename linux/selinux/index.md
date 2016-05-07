---
title: SELinux
type: homepage
authors:
  - Julio Valcarcel
---

## Introduction 

Security Enhanced Linux (SELinux) is a set of security modules for the Linux
kernel. These modules provide mandatory access control on top of the normal
discretionary access control. The Linux kernel provides discretionary access
controls through file permissions. SELinux provides mandatory access controls
by applying labels to every file, process, directory, and port.

### SELinux Labels

To provide granular control over the system it has four kinds of labels.
Through these labels you are given a lot of flexibility. The labels are: 

* User
* Role
* Type
* Sensitivity

To view the SELinux labels you will use `ls -Z`. The -Z flag for ls shows the
SELinux context. The SELinux context is what the combination of those four 
labels is descrided as. Lets say we want to view the SELinux context for 
`/bin/bash` my command would be `ls -Z /bin/bash` which gives us the following
output: 

```bash
$ ls -Z /bin/bash
system_u:object_r:shell_exec_t:s0 /bin/bash
$ 
```
We see from this output that `/bin/bash` has a user label of system_u, role
label of object_r, type of shell_exec_t, and sensitivity of s0. To start with
the only label we will be working with is the type label. 


*WIP*
