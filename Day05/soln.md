# Grant Execute Permissions to `xfusioncorp.sh` on App Server 3

## 1. Connect to App Server 3

From the jump host, connect as `banner`:

```bash
ssh banner@stapp03
```

The first connection displayed the host authenticity prompt. I entered `yes` to add the host key to the known-hosts list, then authenticated.

## 2. Check the script permissions

```bash
cd /tmp
ls -l xfusioncorp.sh
```

Initial output:

```text
---------- 1 root root 40 Oct 12 12:27 xfusioncorp.sh
```

The script had no permissions set.

## 3. Grant permissions to all users

```bash
sudo chmod 755 xfusioncorp.sh
```

## 4. Verify the permissions

```bash
ls -l xfusioncorp.sh
```

Output:

```text
-rwxr-xr-x 1 root root 40 Oct 12 12:27 xfusioncorp.sh
```

## Result

The permissions are now `755`:

- **Owner (`root`):** read, write, execute
- **Group (`root`):** read, execute
- **Others:** read, execute

All users have permission to execute `/tmp/xfusioncorp.sh` on App Server 3.
