# SSH Tunnel - Local and Remote Port Forwarding Explained With Examples

===

There are two ways to create an SSH tunnel, local and remote port forwarding (there’s also dynamic forwarding, but we won’t cover that here). The best way to understand these is by an example, let’s start with local port forwarding.

Imagine you’re on a private network which doesn’t allow connections to a specific server. Let’s say you’re at work and imgur.com is being blocked. To get around this we can create a tunnel through a server which isn’t on our network and thus can access Imgur.
```bash
$ ssh -L 9000:imgur.com:80 user@example.com
```
The key here is -L which says we’re doing local port forwarding. Then it says we’re forwarding our local port 9000 to imgur.com:80, which is the default port for HTTP. Now open your browser and go to http://localhost:9000.

The awesome thing about SSH tunnels is that they are encrypted. Nobody is going to see what sites you’re visiting, they’ll only see an SSH connection to your server.
