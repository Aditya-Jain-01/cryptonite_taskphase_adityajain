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






