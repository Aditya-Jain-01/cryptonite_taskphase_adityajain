# Practicing piping

teaches about input and output redirections.

# Redirecting Output

Use output redirect to write `PWN` to `COLLEGE`.

```
echo PWN>COLLEGE

```

The flag retrived is: `pwn.college{IS1nU4qoJdfZz0pfF_Nh7XUtkVG.dRjN1QDLwQjN0czW}`

# Redirecting more outputs

Use output redirect to write the output of `/challenge/run` in file `myflag`

```
/challenge/run > myflag
```
the output received is:
```
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : myflag
[INFO] - the challenge will output a reward file if all the tests pass : /flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /flag file.

[TEST] You should have redirected my stdout to a file called myflag. Checking...

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
```

Use `cat myflag` to get the flag.

The flag retirved is: `pwn.college{8Ly-G3mxNqO9_ADXtC6_pEp-rYb.dVjN1QDLwQjN0czW}`


# Appending output

redirect the output of `/challenge/run` to `/home/hacker/the-flag` in append mode using `>>` to get the full flag.
```
/challenge>>/home/hacker/the-flag
```

the output is:

```
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /home/hacker/the-flag

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] Good luck!

[TEST] You should have redirected my stdout to a file called /home/hacker/the-flag. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
I will write the flag in two parts to the file /home/hacker/the-flag! I'll do 
the first write directly to the file, and the second write, I'll do to stdout 
(if it's pointing at the file). If you redirect the output in append mode, the 
second write will append to (rather than overwrite) the first write, and you'll 
get the whole flag!

```

Use `cat the-flag` to get the flag.

```
 | 
\|/ This is the first half:
 v 
pwn.college{ESjwqfHMihpls8w7f2yykqqGSk1.ddDM5QDLwQjN0czW}
                              ^
     that is the second half /|\
                              |

If you only see the second half above, you redirected in *truncate* mode (>) 
rather than *append* mode (>>), and so the write of the second half to stdout 
overwrote the initial write of the first half directly to the file. Try append 
mode!
```

# Redirecting errors

Redirect the output of `/challenge/run` to  `myflag` and errors to `instructions` by using `2` for standard error:

```
/challenge/run > myflag 2> instructions
```


Now , `cat` into `myflag` to get the flag.

The falg retrived is: `pwn.college{oI2va2HkTtCY5iOHOIc20Mm4nVo.ddjN1QDLwQjN0czW}`

# Redirecting inputs

Use `echo COLLEGE > PWN` to redirect the output of `echo COLLEGE` to `PWN`

Use `/challenge/run < PWN`  to redirect the file `PWN` as input to `/challenge/run` 

This gives the output: 

```
Reading from standard input...
Correct! You have redirected the PWN file into my standard input, and I read 
the value 'COLLEGE' out of it!
Here is your flag:
pwn.college{ogJ17tFoB8Q0NR9aqMM8x0fGBZN.dBzN1QDLwQjN0czW}
```



# Grepping stored results

redirect the output of `/challenge/run` to `/tmp/data.txt`

```
/challenge/run > /tmp/data.txt
```
the output is:

```
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge will check that output is redirected to a specific file path : /tmp/data.txt
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to a file called /tmp/data.txt. Checking...

[HINT] File descriptors are inherited from the parent, unless the FD_CLOEXEC is set by the parent on the file descriptor.
[HINT] For security reasons, some programs, such as python, do this by default in certain cases. Be careful if you are
[HINT] creating and trying to pass in FDs in python.

[PASS] The file at the other end of my stdout looks okay!
[PASS] Success! You have satisfied all execution requirements.
```

Use `grep pwn.college /tmp/data.txt` , as all flags start with pwn.college.

The flag retrived is:`pwn.college{AE8-L8fkyDrrYdrAuB07IJVUD_M.dhTM4QDLwQjN0czW}`

# Grepping live output

The pipe `|` command can be used to avoide stroing results into a file . It redirects the standard output to another program.

connect `/challenge/run` to `grep pwn.college` by using `|`.

```
/challenge/run | grep pwn.college

```
the output is:
```
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stdout : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stdout to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stdout!
[PASS] Success! You have satisfied all execution requirements.
`pwn.college{sssdn01s2IZP53_QZ4Bpdciwym4.dlTM4QDLwQjN0czW}`

```

# Grepping errors

The error is grepped. Redirect the standard error to standard output using `2>&1`

```
/challenge/run 2>&1 | grep pwn.college
```

the output is:

```
[INFO] WELCOME! This challenge makes the following asks of you:
[INFO] - the challenge checks for a specific process at the other end of stderr : grep
[INFO] - the challenge will output a reward file if all the tests pass : /challenge/.data.txt

[HYPE] ONWARDS TO GREATNESS!

[INFO] This challenge will perform a bunch of checks.
[INFO] If you pass these checks, you will receive the /challenge/.data.txt file.

[TEST] You should have redirected my stderr to another process. Checking...
[TEST] Performing checks on that process!

[INFO] The process' executable is /nix/store/xpq4yhadyhazkcsggmqd7rsgvxb3kjy4-gnugrep-3.11/bin/grep.
[INFO] This might be different than expected because of symbolic links (for example, from /usr/bin/python to /usr/bin/python3 to /usr/bin/python3.8).
[INFO] To pass the checks, the executable must be grep.

[PASS] You have passed the checks on the process on the other end of my stderr!
[PASS] Success! You have satisfied all execution requirements.
pwn.college{8LMSexxk9f7h7RIGh8UISCCQvdE.dVDM5QDLwQjN0czW}
```

# Duplicating piped data with tee

Intercept the commands `/challenge/pwn` and `/challenge/college` by using `tee`

```
/challenge/pwn | tee doracake | /challenge/college
```
now, `cat` into `doracake`

the output is:

```
Usage: /challenge/pwn --secret [SECRET_ARG]

SECRET_ARG should be "o8iOYs61"

```

run the command ` /challenge/pwn --secret o8iOYs61| /challenge/college` to get the flag .

the output is:
```
Processing...
Correct! Passing secret value to /challenge/college...
Great job! Here is your flag:
pwn.college{o8iOYs61AnuFzbnQKPvWsqRg03B.dFjM5QDLwQjN0czW}
```


# Writing to multiple programs

Pipe `/challenge/hack` to `/challenge/the` and `/challenge/planet`

```
/challenge/hack | tee >(/challenge/the) | /challenge/planet

```

this gives the flag: `pwn.college{cIlKA1L9yIQwXNSG3Gcqw-YTeea.dBDO0UDLwQjN0czW}`

# Split-piping stderr and stdout

use `2>` to redirect the stderr to `/challenge/the` and use `|` to redirect stdout to `/challenge/planet`

```
/challenge/hack 2> >(/challenge/the) | /challenge/planet
```
this gives the output:

```
Congratulations, you have learned a redirection technique that even experts 
struggle with! Here is your flag:
pwn.college{QXx9zs0CIP2FaUPrGCN8cAwvYnf.dFDNwYDLwQjN0czW}
```

