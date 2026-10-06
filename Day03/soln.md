# Solution: Disable SSH Root Login on stapp03

## Session Log

```bash
thor@jump-host ~$ ssh banner@stapp03
The authenticity of host 'stapp03 (10.244.29.254)' can't be established.
ED25519 key fingerprint is SHA256:i3VUwPVkqXw57p5mLbyy6tRjfgLMho8vuqbARK5clVQ.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added 'stapp03' (ED25519) to the list of known hosts.
banner@stapp03's password:
[banner@stapp03 ~]$ sudo su -

We trust you have received the usual lecture from the local System
Administrator. It usually boils down to these three things:

    #1) Respect the privacy of others.
    #2) Think before you type.
    #3) With great power comes great responsibility.

[sudo] password for banner:
[root@stapp03 ~] vi /etc/ssh/sshd_config
[root@stapp03 ~] systemctl restart sshd
[root@stapp03 ~] exit
```

## Steps Performed

1. Connected to stapp03 from the jump host as `banner`:
```bash
   ssh banner@stapp03
```
2. Accepted the host key fingerprint (`yes`) and entered the password.
3. Switched to root:
```bash
   sudo su -
```
4. Edited the SSH daemon config:
```bash
   vi /etc/ssh/sshd_config
```
   (Set `PermitRootLogin no`.)
5. Restarted the SSH service to apply the change:
```bash
   systemctl restart sshd
```
6. Exited the root session:
```bash
   exit
```
