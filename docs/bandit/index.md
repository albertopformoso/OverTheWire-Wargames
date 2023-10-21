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

> Password: aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG