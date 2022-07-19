# SSH Tunnels

!!!
***Note:*** You can access the SSH control channel within an SSH session via: `~C`.
!!!

## Local Port Forward

```
ssh -L <local port>:<remote host>:<remote port> user@host
```

## Remote Port Forward

```
ssh -R <SSH server listen port>:<forward target IP>:<listening port> user@host
```

## Dynamic Proxy

```
ssh -D 9050 user@host
```

## SSH Single Pipe Invocation

Run the following command on Kali Linux to create a named pipe locally that can be used for all SSH related matters:

```
ssh user@host -M -S /tmp/%r@%h:%p
```

!!!
Use `-N` and/or `-f` if you want to have SSH not start an interactive session and background the tunnel. 
!!!

## Transfer Files via SSH Pipe

To transfer files via SCP through your currently instantiated SSH pipe use the following command syntax:

```
scp -o 'ControlPath /tmp/%r@%h:%p` <file> user@host:<remote file location>
```

## Close SSH Pipe

```
ssh -S /tmp/%r@%h:%p -O exit user@host
```

## References

SSH Pipe Reference: https://blog.jakubholy.net/2010/09/10/ssh-magic-authorize-only-once-for-multiple-sshscp-invocations/