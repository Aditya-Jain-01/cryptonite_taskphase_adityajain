# Pondering Paths 

Challenge on File Paths.

# The Root

The flag can be retrieved by invoking the `pwn` program, but it resides at the root level, while the shell starts in the home directory. Simply typing `pwn` doesn't work. The correct command is to use the absolute path `/pwn`, which successfully retrieves the flag:
`pwn.college{cdyhuja85BUU4jv0QeZU_NEge-9.dhzN5QDLwQjN0czW}`


# Program and Absolute Paths

This challenge involves navigating through nested directories. The program to retrieve the flag is located inside the folder `challenge`, which is at the root level, and the executable is in the `run` folder inside `challenge`. Using the absolute path `/challenge/run` retrieves the flag:
`pwn.college{8FX6zTmXbrq84qzwcU0GmsaaoUJ.dVDN1QDLwQjN0czW}`


# Position Thyself

Running the previous command doesn’t work because it's executed from the wrong directory. The description specifies that `/usr/aarch64-linux-gnu/include/gnu` is the correct working directory. Therefore, the solution involves changing to the correct directory and running the program:

```
cd /usr/aarch64-linux-gnu/include/gnu
/challenge/run
```
This retrieves the flag: : `pwn.college{YVNTnGeiBcLmgsdQlmMqncQgrUX.dZDN1QDLwQjN0czW}`

# Position Elsewhere

Similar to the previous challenge, the right working directory this time is `/etc/apt/sources.list.d`. 

```
cd /etc/apt/sources.list.d
/challenge/run
```

After navigating there and running the program, the flag is retrieved: `pwn.college{U8UMD04M3aPn9GGxr2YGobrYA8F.ddDN1QDLwQjN0czW}`

# Position yet elsewhere

Again, the challenge requires moving to a different directory, this time /var/log. Once there, running the program retrieves the flag.

```
cd /proc/67
/challenge/run
```
flag: `pwn.college{ApjN-kzbt7L3L_Zdju0GXUGF0aH.dhDN1QDLwQjN0czW}`

# Implicit Relative Paths from Root

The flag can be retrieved using a relative path. The challenge requires running the program from the / directory using its relative path:

```
cd /
challenge/run
```

flag:`pwn.college{cq4yxbNeUIrj-hFVqFdrIfgabqO.dlDN1QDLwQjN0czW}`

# Explicit Relative Paths from Root

Similar to the previous challenge, but now the relative path must begin with `.` . Running the following retrieves the flag.

```
cd /
./challenge/run
```

flag:`pwn.college{4uCeszewFX50E1nrn165Vqgcw9I.dBTN1QDLwQjN0czW}`

# Implicit Relative Path

Here, the working directory must be `/challenge`, but run cannot be executed directly due to Linux safety measures. Using `./run` explicitly retrieves the flag.

```
cd /challenge
./run
```

flag:`pwn.college{U24Qx8jPfTAaZgqITImNB2qRbmq.dFTN1QDLwQjN0czW}`


# Home Sweet Home

In this challenge, the program `/challenge/run` requires an argument that specifies the path of a file where the flag will be written. 
The argument must be an absolute path in the home directory, no longer than 3 characters. The shorthand `~` can be used to represent the home directory:

```
/challenge/run ~/a
```

flag:`pwn.college{cg0ZCje0XL2KLIZcav_ZalJ-rWD.dNzM4QDLwQjN0czW}`




