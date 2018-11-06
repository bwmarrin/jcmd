jcmd - FreeBSD Jail Commands
==========================================

<img align="right" src="https://www.freebsd.org/gifs/doc.jpg">

jcmd is a csh script to help with building and working with FreeBSD jails. 

Jail Commands was wrote mostly from scratch however the script is influenced
by and contains snippts from the FreeBSD handbook, freebsd-update, portsnap, 
mkdir, rmdir, and the ZFS tools.

### Mini FAQ 
Q) Why not just follow the Handbook?
a) Because after a dozen jails (or maybe less) following the Handbook method 
each time might become cumbersome for some.

Q) Why not just use ezJail?
a) Good question! ezJail is thoroughly tested, has more features, is better 
supported, and is probably safer.  You should definitely use it instead.

Q) Wait, what? Why didn't you just use ezJail then?
a) Well. I've always enjoyed "doing it myself" but there are a few reasons.
 
a1) I like understanding the "how and why" and when making Jail Commands I
was able to learn a lot about how jails work and how to set them up. This was
an educational experience for me and it was well worth the time invested.

a2) ezJail is almost like a whole different jail system.  It uses it's own 
configuration, rc scripts, and commands. I wanted to stick to using the 
default FreeBSD configuration methods and command line tools where possible.

a3) ezJail does not seem to work with existing jails made using the FreeBSD
handbook method or the existing FreeBSD jail commands and I wanted a tool 
that would.

Q) What's your goal with Jail Commands?
a) To expand upon the default FreeBSD jail commands and configuration methods
with additional commands for creating and working with jails that work along 
side the normal FreeBSD jail commands.

### Installing
This is just a simple single file script.  You can clone the repo to your system
or just download the script file itself and copy it to anywhere on your system
you like.  I recommend /opt/jcmd as a good installation folder.

Once you have the script coped to your system you can use the below command to
create symbolic links in /usr/local/bin for the script.

```
jcmd mklinks
```

### Usage
```
usage: `basename $0` [options] command [jailname]

Options:
 -d <destdir>   -- Destination directory
 -j <threads#>  -- Number of Threads to use

Commands:
 mklinks -- Create symbolic links in /usr/local/bin for jcmds
 rmlinks -- Remove symbolic links in /usr/local/bin for jcmds 
 lslinks -- List symbolic links in /usr/local/bin for jcmds

 buildworld   -- Build userland from /usr/src source 
 installworld -- Install userland from /usr/src source
 distribution -- Install distrubution from /usr/src/etc

 make      -- Make a new jail
 up        -- Bring jail up
 down      -- Shutdown jail
 restart   -- Restart a jail
 shell|sh  -- Open shell inside jail
 login     -- Login to jail
 remove    -- Remove jail files 
 update    -- Update a jail to latest patch level
 ids       -- Run IDS test on jail
```
