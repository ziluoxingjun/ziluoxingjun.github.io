# SSH Tunnel - Local and Remote Port Forwarding Explained With Examples

There are two ways to create an SSH tunnel, local and remote port forwarding (there’s also dynamic forwarding, but we won’t cover that here). The best way to understand these is by an example, let’s start with local port forwarding.

Imagine you’re on a private network which doesn’t allow connections to a specific server. Let’s say you’re at work and imgur.com is being blocked. To get around this we can create a tunnel through a server which isn’t on our network and thus can access Imgur.

```bash
$ ssh -L 9000:imgur.com:80 user@example.com
```

The key here is `-L` which says we’re doing local port forwarding. Then it says we’re forwarding our local port `9000` to `imgur.com:80`, which is the default port for HTTP. Now open your browser and go to http://localhost:9000.

The awesome thing about SSH tunnels is that they are encrypted. Nobody is going to see what sites you’re visiting, they’ll only see an SSH connection to your server.

## SSH Tunnel - Local and Remote Port Forwarding Explained With Examples

Another good example is if you need to access a port on your server which can only be accessed from `localhost` and not remotely.

An example here is when you need to connect to a database console, which only allows local connection for security reasons. Let’s say you’re running PostgreSQL on your server, which by default listens on the port `5432`.

$ ssh -L 9000:localhost:5432 user@example.com
The part that changed here is the localhost:5432, which says to forward connections from your local port 9000 to localhost:5432 on your server. Now we can simply connect to our database.

$ psql -h localhost -p 9000
Now let’s stop here for a little bit an explain what is actually going on. In the first example the 9000:imgur.com:80 is actually saying forward my local port 9000 to imgur.com at port 80. You can imagine SSH on your server actually making a connection (a tunnel) between those two ports, one on your local machine, and one on the target destination.

If we however say something like 9000:localhost:5432, it means localhost from the server’s perspective, not localhost on your machine. This means forward my local port 9000 to port 5432 on the server, because when you’re on the server, localhost means the server itself.

This might be a bit confusing, but it is important to understand what the syntax actually means here.
