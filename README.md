# OverTheWire-Natas - J0nan <!-- omit in toc -->

# Table of Content <!-- omit in toc -->
- [Natas levels](#natas-levels)
  - [Level 0](#level-0)
    - [Access](#access)
    - [Password](#password)
  - [Level 1](#level-1)
    - [Access](#access-1)
    - [Password](#password-1)
  - [Level 2](#level-2)
    - [Access](#access-2)
    - [Password](#password-2)
  - [Level 3](#level-3)
    - [Access](#access-3)
    - [Password](#password-3)
  - [Level 4](#level-4)
    - [Access](#access-4)
    - [Password](#password-4)
  - [Level 5](#level-5)
  - [Level 6](#level-6)
  - [Level 7](#level-7)
  - [Level 8](#level-8)
  - [Level 9](#level-9)
  - [Level 10](#level-10)
  - [Level 11](#level-11)
  - [Level 12](#level-12)
  - [Level 14](#level-14)
  - [Level 15](#level-15)
  - [Level 16](#level-16)
  - [Level 17](#level-17)
  - [Level 18](#level-18)
  - [Level 19](#level-19)
  - [Level 20](#level-20)
  - [Level 21](#level-21)
  - [Level 22](#level-22)
  - [Level 23](#level-23)
  - [Level 24](#level-24)
  - [Level 25](#level-25)
  - [Level 26](#level-26)
  - [Level 27](#level-27)
  - [Level 28](#level-28)
  - [Level 29](#level-29)
  - [Level 30](#level-30)
  - [Level 31](#level-31)
  - [Level 32](#level-32)
  - [Level 33](#level-33)


# Natas levels

Here I will put the access username and password for each level, and what I did and why to find the password for the next level.

https://overthewire.org/wargames/natas/

## Level 0

### Access

http://natas0.natas.labs.overthewire.org/

username: natas0

password: natas0

### Password
Viewing the source code of the web (Ctrl + U), we can find the password for the next level.
```
g9D9cREhslqBKtcA2uocGHPfMZVzeFK6
```

## Level 1

### Access

http://natas1.natas.labs.overthewire.org/

username: natas1

password: g9D9cREhslqBKtcA2uocGHPfMZVzeFK6

### Password
Viewing the source code of the web (Ctrl + U), we can find the password for the next level.
```
h4ubbcXrWqsTo7GGnnUMLppXbOogfBZ7
```

## Level 2

### Access

http://natas2.natas.labs.overthewire.org/

username: natas2

password: h4ubbcXrWqsTo7GGnnUMLppXbOogfBZ7

### Password
Viewing the source code of the web (Ctrl + U), we find an image located in `files/pixel.png`. As you can see, the server is serving an image on the folder `files` so we can try removing the `pixel.png` from the url (http://natas2.natas.labs.overthewire.org/files). There we can see the files on the folder. If we open the file named `users.txt` we find some users and their password, there we have the password for natas3.

```
G6ctbMJ5Nb4cbFwhpMPSvxGHhQ7I6W8Q
```

## Level 3

### Access

http://natas3.natas.labs.overthewire.org/

username: natas3

password: G6ctbMJ5Nb4cbFwhpMPSvxGHhQ7I6W8Q

### Password
Viewing the source code of the web (Ctrl + U), we see they left us a clue, as we can see a comment that says: `<!-- No more information leaks!! Not even Google will find it this time... -->`. This is telling us to look at the `robots.txt` file of the web. This files is used by search engine crawlers, mainly to avoid overloading your site with requests and indicate whether certain user agents (web-crawling software) can or cannot crawl parts of a website.

Accessing http://natas3.natas.labs.overthewire.org/robots.txt we can see that there is a path disallow for every User-Agent, `/s3cr3t/`. With these we access http://natas3.natas.labs.overthewire.org/s3cr3t/. There as on the prior level, we find a file called `users.txt`, if we open it we find the password for natas4.

```
tKOcJIbzM4lTs8hbCmzn5Zr4434fGZQm
```

## Level 4

### Access

http://natas4.natas.labs.overthewire.org/

username: natas4

password: G6ctbMJ5Nb4cbFwhpMPSvxGHhQ7I6W8Q

### Password

## Level 5

## Level 6

## Level 7

## Level 8

## Level 9

## Level 10

## Level 11

## Level 12

## Level 14

## Level 15

## Level 16

## Level 17

## Level 18

## Level 19

## Level 20

## Level 21

## Level 22

## Level 23

## Level 24

## Level 25

## Level 26

## Level 27

## Level 28

## Level 29

## Level 30

## Level 31

## Level 32

## Level 33
