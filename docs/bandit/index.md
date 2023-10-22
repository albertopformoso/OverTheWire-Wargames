# Bandit

## Level 0

The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

```sh
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

> Password: bandit0

## Level 0 → Level 1

The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

```sh
cat readme
```

> Output: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

## Level 1 → Level 2

The password for the next level is stored in a file called - located in the home directory

```sh
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

> Password: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

```sh
cat "./-"
```

> Output: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

## Level 2 → Level 3

The password for the next level is stored in a file called spaces in this filename located in the home directory

```sh
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

> Password: rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

```sh
cat "./spaces in this filename"
```

> Output: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

## Level 3 → Level 4

The password for the next level is stored in a hidden file in the inhere directory.

```sh
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

> Password: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

```sh
ls -la
ls -la inhere/
cat inhere/.hidden
```

> Output: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

## Level 4 → Level 5

The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

```sh
ssh bandit4@bandit.labs.overthewire.org -p 2220
```

> Password: 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

```sh
find ./inhere -type f -exec file {} + | grep "ASCII"
```

```sh
cat ./inhere/-file07
```

> Output: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

## Level 5 → Level 6

The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:

human-readable
1033 bytes in size
not executable

```sh
ssh bandit5@bandit.labs.overthewire.org -p 2220
```

> Password: lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

```sh
find ./inhere -type f ! -executable -size 1033c
```

```sh
cat ./inhere/maybehere07/.file2
```

> Output: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

## Level 6 → Level 7

The password for the next level is stored somewhere on the server and has all of the following properties:

owned by user bandit7
owned by group bandit6
33 bytes in size

```sh
ssh bandit6@bandit.labs.overthewire.org -p 2220
```

> Password: P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

```sh
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
```
Here's a breakdown of the command:

+ `/`: Start the search from the root directory.
+ `-user bandit7`: Look for files owned by the user bandit7.
+ `-group bandit6`: Look for files owned by the group bandit6.
+ `-size 33c`: Look for files that are 33 bytes in size. The c stands for bytes.
+ `2>/dev/null`: This part of the command redirects all error messages (like "Permission denied") to /dev/null so that you only see valid results.

```sh
cat /var/lib/dpkg/info/bandit7.password
```

> Output: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

## Level 7 → Level 8

The password for the next level is stored in the file data.txt next to the word millionth

```sh
ssh bandit7@bandit.labs.overthewire.org -p 2220
```

> Password: z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

```sh
cat data.txt | grep "millionth"
```

> Output: millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP

## Level 8 → Level 9

The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

The password for the next level is stored in the file data.txt next to the word millionth

```sh
ssh bandit8@bandit.labs.overthewire.org -p 2220
```

> Password: TESKZC0XvTetK0S9xNwm25STk5iWrBvP

```sh
sort data.txt | uniq -u
```

[`uniq`](https://www.ibm.com/docs/sl/aix/7.2?topic=u-uniq-command) flag `-u` displays only the unrepeated lines.

> Output: EN632PlfYiZbn3PhVK3XOGSlNInNE00t

## Level 9 → Level 10

The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

```sh
ssh bandit9@bandit.labs.overthewire.org -p 2220
```

> Password: EN632PlfYiZbn3PhVK3XOGSlNInNE00t

=== "strings"

    **Use strings to extract readable strings**

    The strings command in Linux is used to extract printable strings from a binary file. This is helpful when trying to locate human-readable content within such files.

    ```sh
    strings data.txt | grep "==="
    ```

=== "grep"

    The -a option in grep allows it to process a binary file as if it were text. When dealing with files that might contain a mix of binary data and human-readable strings, the -a (or --text) option can be quite useful.

    Using grep -a "===" data.txt will search the file for lines containing the pattern ===, treating the file as text, regardless of its actual content. Given your level's goal, this command should be effective in identifying lines with several '=' characters, leading you to find the password.

    ```sh
    grep -a "===" data.txt
    ```

```log "Output"
x]T========== theG)"
========== passwordk^
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```
