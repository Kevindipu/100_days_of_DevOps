## Command

```bash
sudo chmod a+x /tmp/xfusioncorp.sh
```

## Explanation

* `chmod`: Changes file permissions.
* `a`: Applies to all users (owner, group, and others).
* `+x`: Adds execute permission without changing existing permissions.

## Verify Permissions

```bash
ls -l /tmp/xfusioncorp.sh
```

The permissions should include `x` for the owner, group, and others.
