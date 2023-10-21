# Bandit

<!-- TOC -->

- [Bandit](#bandit)
    - [Passwords](#passwords)
    - [Level 0](#level-0)
    - [Level 0 → Level 1](#level-0-%E2%86%92-level-1)

<!-- /TOC -->

## Passwords

| Level             | Password                         |
| :---------------- | :------------------------------: |
| Level 0           | bandit0                          |
| Level 0 → Level 1 | NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL |


## Level 0

The goal of this level is for you to log into the game using SSH. The host to which you need to connect is bandit.labs.overthewire.org, on port 2220. The username is bandit0 and the password is bandit0. Once logged in, go to the Level 1 page to find out how to beat Level 1.

> Password: bandit0

```sh
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

## Level 0 → Level 1

The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

> Password: bandit0

```sh
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

```sh
cat readme
```

> Output: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
