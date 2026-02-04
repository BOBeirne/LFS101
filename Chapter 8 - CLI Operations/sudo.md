- sudo capabilities provide user with admin privileges when required (super user)
- It may need to be set up separately after system installation but a lot of distribution will configure it automatically

### Setting up sudo

```bash
su password
# ******
echo "username ALL=(ALL) ALL" > /etc/sudoers.d/username # create config file enabling sudo for specified user

chmod 440 /etc/sudoers.d/username # change file permissions
```

