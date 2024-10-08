# Digesting Documentation

understanding what is documentation.

# Learning From Documentation

Run the command `/challenge/challenge` with the argument `--giveflag` 
```
/challenge/challenge --giveflag
```

This retrives the flag: `pwn.college{s9QIqJhaQcwoaI0OPiOsScUK6FD.dRjM5QDLwQjN0czW}`

# Learning Complex Usage

Run the command `/challenge/challenge` with argument `--printfile` to print the content of the argument of `--printfile`. 
To get the flag the argument used is`/flag`

```
/challenge/challenge --printfile /flag
```
Thia retrives the flag: `pwn.college{MOP_votKEugKXcpfeEWrTboFfJV.dVjM5QDLwQjN0czW}`

# Reading Manuals

Run the `man` command with `challenge`
The resulting description is:
```
DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --ldkvwx NUM
              print the flag if NUM is 844
```
To get the flag we must use `/challenge/challenge --ldkvwx 844 `

The flag retrived is: ` pwn.college{8TldEYKCkvQHw4EHPxJLFOybDhQ.dRTM4QDLwQjN0czW}`

# Searching Manuals

Run the `man` command with `challenge` argument to get the desscription.
Use the `/flag` command to search flag.
```
 --getnk
              This argument will give you the flag!
```
Run `/challenge/challenge --getnk` to get the flag.
The flag retrived is: `pwn.college{AS72zPPSkduZIhNH6xROrQsGEMc.dVTM4QDLwQjN0czW}`

# Searching for Manuals

Run the `man man` command and check the examples.

```
 man -k printf
           Search the short descriptions and manual page names for the keyword printf as
           regular expression.  Print out any matches.  Equivalent to apropos printf.

       
```
the `man -k printf ` command can be used to find manual pages using keywords.
Using command `man -k printf` where `flag` is the keyword.

```



dpkg-buildflags (1)  - returns build flags to use during package build
Dpkg::BuildFlags (3perl) - query build flags
fegetexceptflag (3)  - floating-point rounding and exception handling
fesetexceptflag (3)  - floating-point rounding and exception handling
i386 (8)             - change reported architecture in new program environment and/or se...
ioctl_iflags (2)     - ioctl() operations for inode flags
linux32 (1)          - change reported architecture in new program environment and/or se...
linux64 (1)          - change reported architecture in new program environment and/or se...
nqtigrewuk (1)       - print the flag!
pcap-config (1)      - write libpcap compiler and linker flags to standard output
security_compute_av_flags (3) - query the SELinux policy database in the kernel
security_compute_av_flags_raw (3) - query the SELinux policy database in the kernel
set_matchpathcon_flags (3) - set flags controlling the operation of matchpathcon or matc...
set_matchpathcon_invalidcon (3) - set flags controlling the operation of matchpathcon or...
set_matchpathcon_printf (3) - set flags controlling the operation of matchpathcon or mat...
setarch (1)          - change reported architecture in new program environment and/or se...
setarch (8)          - change reported architecture in new program environment and/or se...
x86_64 (8)           - change reported architecture in new program environment and/or se...


```
Use `man nqtigrewuk` to get the man page of challenge program.
```
DESCRIPTION
       Output the flag when called with the right arguments.

       --fortune
              read a fortune

       --version
              output version information and exit

       --nqtigr NUM
              print the flag if NUM is 540
```
Run `/challenge/challenge --nqtigr 540` to get the flag.
The Flag retrived is: `pwn.college{A-Vn-qTOtig5rSeOPwukaTCWGcw.dZTM4QDLwQjN0czW}`

# Helpful Programs

Use `/challenge/challenge --help` to get :

```
usage: a challenge to make you ask for help [-h] [--fortune] [-v] [-g GIVE_THE_FLAG] [-p]

optional arguments:
  -h, --help            show this help message and exit
  --fortune             read your fortune
  -v, --version         get the version number
  -g GIVE_THE_FLAG, --give-the-flag GIVE_THE_FLAG
                        get the flag, if given the correct value
  -p, --print-value     print the value that will cause the -g option to give you the
                        flag

```
Run `/challenge/challenge -p` to get value to use `-g`

```
The secret value is: 357
```
Use `/challenge/challenge -g 354` to get the flag.
The flag retrived is: `pwn.college{kjas3xBAEaNwhKlRZOKnJf5D7oP.ddjM4QDLwQjN0czW}`

# Help for Builtins

Run the `help challenge` command to get:

```
challenge: challenge [--fortune] [--version] [--secret SECRET]
    This builtin command will read you the flag, given the right arguments!
    
    Options:
      --fortune         display a fortune
      --version         display the version
      --secret VALUE    prints the flag, if VALUE is correct

    You must be sure to provide the right value to --secret. That value
    is "cRbTqEFo".

```
Now, run `challenge --secret cRbTqEFo` to get  the flag.

The flag retrived is: `pwn.college{cRbTqEFoyFiwyqSH1uVCfPXhZit.dRTM5QDLwQjN0czW}`

