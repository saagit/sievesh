# sievesh
A self contained Python 3 script implementing a managesieve client to administer Sieve scripts à la ftp clients.

## Usage
sievesh is a Python 3 script that implements an interactive
managesieve client.  I use it to administer my Sieve scripts on
mailbox.org.  The authentication may or may not work with other Sieve
servers.

sievesh is a command line utility:
```
usage: sievesh [-h] [-F CONFIG_FILE] [-c CONFIG_SECTION] [--host HOST]
               [--port PORT] [--user USER] [--password PASSWORD] [-d] [-v]

Self contained script to implement a shell to talk to a Sieve sever.

optional arguments:
  -h, --help            show this help message and exit
  -F CONFIG_FILE, --config-file CONFIG_FILE
                        The configuration file to use.
  -c CONFIG_SECTION, --config-section CONFIG_SECTION
                        The section of the configuration file to use.
  --host HOST           The Sieve server host to connect to.
  --port PORT           The port to connect to on the server.
  --user USER           The user to connect as.
  --password PASSWORD   The password will be prompted for if not given.
  -d, --debug           Show interactions with the Sieve server.
  -v, --verbose         Show connection information.
```

After running sievesh and entering your password for the Sieve server,
you will presented with a `> ` prompt and sievesh will wait for your
commands.  The commands that sievesh accepts are:

command | description
------- | -----------
help | List available commands or a given command's usage.
ls | List the scripts on the Sieve server.
pact | Print name of active script.
cact | Change active script or inactivate all scripts.
get | Make a local copy of a Sieve server script.
put | Copy a local file to a Sieve server script.
cp | Copy a script to a new script.
mv | Move a script to a new name.
rm | Remove one or more scripts.
hashsum | Calculate hashes of Sieve server scripts.
ci | Print user@host:port of current connection.
caps | List Sieve server capabilites.
shell or ! | Execute a shell command on the local system
_ | comments; all arguments are ignored
exit, logout, quit or EOF | Logout from Sieve server and exit.
