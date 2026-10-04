# Create Temporary User on App Server 2

## Solution

### 1. Connect to App Server 2

From the jump host:

```bash
ssh steve@stapp02
```

### 2. Create the User

On App Server 2, create the user with the required expiry date:

```bash
sudo useradd -e 2027-02-17 kareem
```

Enter the `sudo` password when prompted.

## Result

The user `kareem` is created on App Server 2 with an account expiry date of `2027-02-17`.
