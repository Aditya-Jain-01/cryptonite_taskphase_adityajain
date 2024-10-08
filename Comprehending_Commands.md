# Comprehending Commands

Understanding Linux commands

# cat: Not Just for Pets!
The flag file, located in the home directory, contains the necessary flag. You can read the file's contents using its relative path as an argument with the `cat` command. 

```
cat flag
```
This retrives the flag: `pwn.college{Y7Xwrt1beETfKrXfh0zRKIynmUl.dFzN1QDLwQjN0czW}`

# catting absolute paths

This time, the flag file is in the root directory. Similar to the previous challenge, but using the absolute path:

```
cat /flag
```

This retrives the flag: `pwn.college{03S-FSTJD-JPRvzyNo6og07l89J.dlTM5QDLwQjN0czW}`

# more catting practice

The flag file is now located in `/opt/rappel/t/flag` . Again, use the absolute path:

```
cat /opt/rappel/t/flag
```

This retrives the flag: `pwn.college{MuWB38fWdtzt5ArD8vAHUs2ek2i.dBjM5QDLwQjN0czW}`

# grepping for a needle in a haystack
The flag is hidden within `/challenge/data.txt`, a file with 100,000 lines. To retrieve the line with the flag, use grep to search for the flag pattern:

```
grep pwn.college /challenge/data.txt
```

This retrives the flag: `pwn.college{AjaHiHZHSkNAgaVATXlyKKTNbnA.ddTM4QDLwQjN0czW}`

# listing files

In the `/challenge directory`, the run file has been renamed. First, change to the directory and use `ls` to list the files:

```
cd /challenge
ls
```

The renamed file is `28866-renamed-run-28119`.

```
/challenge/28866-renamed-run-28119
```
This retrives the flag: `pwn.college{kzbpvsATLxEcHSlHrK4PBV1chxt.dhjM4QDLwQjN0czW}`

# touching files

To make `/challenge/run` work, two files `/tmp/pwn` and `/tmp/college` need to be created. You can use the `touch` command for this:

```
cd /tmp
touch pwn
touch college
/challenge/run
```

This retrives the flag: `pwn.college{gdpq0cxzUK0P7KkU417L2rv-2VQ.dBzM4QDLwQjN0czW}`

# Removing Files

Use `touch ` command to create a file `delete_me`
Now,use the `rm` command with `delete_me` to remove the file.

Run `/challenge/check` to get the flag.

The flag retrived is:`pwn.college{EtP73dj0kWCn-izssUv2OMmSTkt.dZTOwUDLwQjN0czW}`

# Hidden Files

Go to root directory . Use the ls -a coomand to find the hidden file.
Find the file and read it using `cat`.

```
cd /
ls -a
cat .flag-8525259502670
```

The flag retrived is:`pwn.college{AuNxLgCgu_y7WVX9JQ0p1oHRGeU.dBTN4QDLwQjN0czW}`

# An Epic Filesystem Quest

The quest begins in the root directory: `cd /`

Upon using `ls`, a file called REVELATION is visible.

`cat REVELATION` reads:

**Great sleuthing!**
The next clue is in: `/opt/linux/linux-5.4/drivers/misc/sgi-xp`

Navigating to `/opt/linux/linux-5.4/drivers/misc/sgi-xp` and running `ls` reveals a file named GIST. 

`cat GIST` reads:

**Tubular find!**
The next clue is in: `/opt/linux/linux-5.4/include/config/snd/support`

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.

After changing to `/opt/linux/linux-5.4/include/config/snd/support`, running `ls` reveals a file called `README`.

`cat README` reads:

The next clue is in: `/opt/aflplusplus/qemu_mode/qemuafl/.gitlab-ci.d/edk2`

The next clue is **hidden** --- its filename starts with a `.` character. Use special options to `ls` to find it.

Running `ls -a` in the directory reveals a hidden file named `.WHISPER`.

`cat .WHISPER` reads:

**Tubular find!**
The next clue is in: `/usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/Lower`

Watch out! The next clue is **trapped**. You must read it without `cd`-ing into the directory, or the clue will self-destruct!

Running `ls /usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/Lower` shows a file called `HINT-TRAPPED`.

`cat /usr/lib/x86_64-linux-gnu/perl-base/unicore/lib/Lower HINT-TRAPPED` reads:

**Yahaha, you found me!**
The next clue is in: `/usr/local/lib/python3.8/dist-packages/importlib_resources/compat/__pycache__
`

Watch out! The next clue is **trapped**. You'll need to read it out without `cd`ing into the directory; otherwise, the clue will self destruct!

Upon running `ls /usr/local/lib/python3.8/dist-packages/importlib_resources/compat/__pycache__`,` reveals a file named MEMO-TRAPPED.

`cat /usr/local/lib/python3.8/dist-packages/importlib_resources/compat/__pycache__/ MEMO-TRAPPED` reads:

The next clue is in: `/opt/aflplusplus/nyx_mode/QEMU-Nyx/tests/data/acpi`

The next clue is **hidden** --- its filename starts with a '.' character. You'll need to look for it using special options to 'ls'.


Running `cd /opt/aflplusplus/nyx_mode/QEMU-Nyx/tests/data/acpi` and `ls -a` shows a file named `.CUE`.

`cat .CUE` reads:


**Congratulations**, you found the clue!
The next clue is in: `/usr/include/gc`

After entering `/usr/include/gc`, running `ls -a` reveals a file called INFO.

`cat INFO` reads:

**Great sleuthing!**
The next clue is in: /usr/share/gap/doc/tut

The next clue is **delayed** --- it will not become readable until you enter the directory with 'cd'.

Running `cd /usr/share/gap/doc/tut` and `ls -a` shows a file named `SPOILER`.

`cat SPOILER` gives:

**CONGRATULATIONS!** Your perseverance has paid off, and you have found the flag!

The flag is: `pwn.college{ojrDir7JoWDpC_u_6-SRvXah5Ed.dljM4QDLwQjN0czW}`


# Making Directories

First `cd` to `/tmp`
Create a new directory `pwn` using `mkdir`

```
mkdir pwn
```
Go to `pwn` and create a file `college`.
Run `challenge/run` to get the flag.

The flag retrived is: `pwn.college{8nSCjeT9jCN9c154vncpJqiqiQK.dFzM4QDLwQjN0czW}`


# Finding diretories 

use command `find` to find directories.
```
find / -name flag
find: ‘/root’: Permission denied
find: ‘/etc/ssl/private’: Permission denied
find: ‘/tmp/tmp.G9qthVCks5’: Permission denied
/usr/local/share/radare2/5.9.5/flag
/usr/local/lib/python3.8/dist-packages/pwnlib/flag
find: ‘/var/cache/apt/archives/partial’: Permission denied
find: ‘/var/cache/ldconfig’: Permission denied
find: ‘/var/cache/private’: Permission denied
find: ‘/var/log/private’: Permission denied
find: ‘/var/log/apache2’: Permission denied
find: ‘/var/log/mysql’: Permission denied
find: ‘/var/lib/apt/lists/partial’: Permission denied
find: ‘/var/lib/mysql-keyring’: Permission denied
find: ‘/var/lib/php/sessions’: Permission denied
find: ‘/var/lib/private’: Permission denied
find: ‘/var/lib/mysql-files’: Permission denied
find: ‘/var/lib/mysql’: Permission denied
find: ‘/run/mysqld’: Permission denied
find: ‘/run/sudo’: Permission denied
find: ‘/proc/tty/driver’: Permission denied
find: ‘/proc/1/task/1/fd’: Permission denied
find: ‘/proc/1/task/1/fdinfo’: Permission denied
find: ‘/proc/1/task/1/ns’: Permission denied
find: ‘/proc/1/fd’: Permission denied
find: ‘/proc/1/map_files’: Permission denied
find: ‘/proc/1/fdinfo’: Permission denied
find: ‘/proc/1/ns’: Permission denied
find: ‘/proc/7/task/7/fd’: Permission denied
find: ‘/proc/7/task/7/fdinfo’: Permission denied
find: ‘/proc/7/task/7/ns’: Permission denied
find: ‘/proc/7/fd’: Permission denied
find: ‘/proc/7/map_files’: Permission denied
find: ‘/proc/7/fdinfo’: Permission denied
find: ‘/proc/7/ns’: Permission denied
/opt/linux/linux-5.4/drivers/pnp/pnpbios/flag
/opt/pwndbg/.venv/lib/python3.8/site-packages/pwnlib/flag
/opt/radare2/libr/flag
/nix/store/pmvk2bk4p550w182rjfm529kfqddnvh3-python3.11-pwntools-4.12.0/lib/python3.11/site-packages/pwnlib/flag
/nix/store/1yagn5s8sf7kcs2hkccgf8d0wxlrv5sz-radare2-5.9.0/share/radare2/5.9.0/flag

```


Use `cat /opt/linux/linux-5.4/drivers/pnp/pnpbios/flag` to get the flag.

The flag retrived is: `pwn.college{8aO2sEyNtbcd0e2Q4DdoeEGpwP_.dJzM4QDLwQjN0czW}`


# Linking Files

we read `/home/hacker/not-the-flag` file by making the file `flag` point towards it.

Use the command `ln -s /flag /home/hacker/not-the-flag`.
Run `challenge/catflag` to get the flag.

The flag retrived is:`pwn.college{MkUcw0FFFyYqX8ZNTzXC6cCDmlL.dlTM1UDLwQjN0czW}`





