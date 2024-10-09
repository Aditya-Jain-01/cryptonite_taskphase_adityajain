# File Globbing

Understanding what is globbing.

# Matching with *

Use `cd` with `/c*` to keep the keep the character length minimum to 4.

Now, run `/challenge/run` to get the flag.

The flag retrived is: `pwn.college{QbpRa76e8pergXsP8CnhfTTytwi.dFjM4QDLwQjN0czW}`

# Matching with ?

The `?` act as single character wild card. 
Use `cd /?ha??enge` to change the directory without using 'c' and 'l'.
Now, run `/challenge/run` to get the flag.

The flag retrived is:`pwn.college{gFSkH4sYWKN3WONnjujZJ5uDkNA.dJjM4QDLwQjN0czW}`

# Matching with []

The `[]` is similar to `?`. Characters are specified within the brackets. 

Change directory to `/challenge/files` by `cd /challenge/files`

Now, use `/challenge/run file_[bash]` so that only one argument is used.

The flag retrived is: `pwn.college{gM09eZPP6Hc8WWa33qlkmvydq0I.dNjM4QDLwQjN0czW}`

# Matching Paths with []

Run `/challenge/run` from the home directory and using a single argumrnt

```
/challenge/run /challenge/files/file_[bash]
```

This retrives the flag: `pwn.college{YJgnWx9dBbL4qh5W9jV0UKfy6o6.dRjM4QDLwQjN0czW}`


# Mixing Globes
`cd` to `/challenges/files`.

for extracting files named as `challenge , education , pwning` , use`[]` to wildcard initials and `*` to wildcard remaining characters.

```
/challenge/run [cep]*
```
The flag retrived is: `pwn.college{M6SaXhUMtnkLBRN2qTVTKpAjQo_.dVjM4QDLwQjN0czW}`

# Exclusionary globbing

Run `cd /challenges/files` to cahnge directory.
To print the files which are not starting with `p,w,n` , use `!` or `^` with `[]`.

```
/challenge/run [^pwn]*
```

The flag retrived is: `pwn.college{QUvrdFoizJAluEytVnEGEzopoMq.dZjM4QDLwQjN0czW}`



