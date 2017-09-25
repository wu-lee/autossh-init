autossh init script
-------------------

## NAME

autossh init - an autossh init.d script for Centos

## SYNOPSIS

autossh is a program to start a copy of ssh and monitor it, restarting
it as necessary should it die or stop passing traffic.

This is simply an init script to configure and start autossh on boot.

To install the script:

    cp autossh.init /etc/init.d/autossh
    chmod 0644 /etc/init.d/autossh
    mkdir /etc/autossh

Create configs in `/etc/autossh` as per the example `autossh.config`.
More information at the above author's website, see URL below. (Note:
except use the .config extension, used to distinguish configs from
tilda/backup files etc.)

To start and stop tunnels:

    /etc/init.d/autossh start <configname>
    /etc/init.d/autossh stop <configname>

Specifying a config name is optional, applies to all configs if unspecified.

To automatically start on boot:

    chkconfig --add autossh


## Note from the committer

Currently this is simply a verbatim copy from:

https://surniaulula.com/2012/12/10/autossh-startup-script-for-multiple-tunnels/

Therefore all credit goes to the author, JS Morrisset.  I have simply
added it to Git version control, in the spirit of GPL, and added this README.

-- Nick Stokoe

## SEE ALSO

- autossh - http://www.harding.motd.ca/autossh/
- https://surniaulula.com/2012/12/10/autossh-startup-script-for-multiple-tunnels/
- ServerAliveInterval and disabling monitoring:
  https://www.everythingcli.org/ssh-tunnelling-for-fun-and-profit-autossh/
