# OpenSSH (Secure Shell)

- OpenSSH is a remote management tool that gives you access to run commands on another machine.
- Uses default port 22 as ssh port.
- Use `which ssh` to check ssh client is installed.
- Use `ssh <username>@serveripaddr` to connect
- Check /var/log/auth.log for ssh connections

## Key Management

- Use `ssh-keygen` to generate public/private keys for server management. Require to use passphrase as additional layer of security.

```ps
ssh-keygen -t ed25519 -a 200 -C "you@host" -f $HOME/<keyid>_ed25519
```


## Troubleshooting

- Check network layer


## Best Practice

- Disable password authentication. Only use public/private key to access servers.
- Add passphrase for the ssh keys as additional layer of security.
- Change the SSH port. For example, change port num 22 to port num 2222


## Reference

- [OpenSSH Full Guide - Everything you need to get started!](https://www.youtube.com/watch?v=YS5Zh7KExvE)