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
    - [Access](#access-5)
    - [Password](#password-5)
  - [Level 6](#level-6)
    - [Access](#access-6)
    - [Password](#password-6)
  - [Level 7](#level-7)
    - [Access](#access-7)
    - [Password](#password-7)
  - [Level 8](#level-8)
    - [Access](#access-8)
    - [Password](#password-8)
  - [Level 9](#level-9)
    - [Access](#access-9)
    - [Password](#password-9)
  - [Level 10](#level-10)
    - [Access](#access-10)
    - [Password](#password-10)
  - [Level 11](#level-11)
    - [Access](#access-11)
    - [Password](#password-11)
  - [Level 12](#level-12)
    - [Access](#access-12)
    - [Password](#password-12)
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

password: tKOcJIbzM4lTs8hbCmzn5Zr4434fGZQm

### Password
For this challenge I used [Burp]([https://](https://portswigger.net/burp/communitydownload)) to capture and modify the petitions sent, and modify them before they are sent. We need to do this, because the web page is telling us that we can only access from `http://natas5.natas.labs.overthewire.org/`.

If we capture the traffic in Burp when we refresh the page, we can see a field which is: `Referer: http://natas4.natas.labs.overthewire.org/index.php`. In order to access the password, we need to change it to: `Referer: http://natas5.natas.labs.overthewire.org/index.php` and then the page will load showing us the password.

```
Z0NsrtIkJoKALBCLi5eqFfcRN82Au2oD
```

## Level 5

### Access

http://natas5.natas.labs.overthewire.org/

username: natas5

password: Z0NsrtIkJoKALBCLi5eqFfcRN82Au2oD

### Password

For this challenge we see the web page is telling us that we are not logged in, this is telling us that the web page is looking at something to check whether we are logged in or not. With this information I decided to look at the cookies. There I can see that there is a cookie named `loggedin` with a value of `0`. I change the value to `1` and then refresh the page. Then the page is showing us the password for natas6.

```
fOIvE0MDtPTgRhqmmvvAOt2EfXR6uQgR
```

## Level 6

### Access

http://natas6.natas.labs.overthewire.org/

username: natas6

password: fOIvE0MDtPTgRhqmmvvAOt2EfXR6uQgR

### Password

If we look at the source code of the web, we can see that the web is including a file named `includes/secret.inc` with this we can try accessing the file accessing the url http://natas6.natas.labs.overthewire.org/includes/secret.inc there we can find the secret. With that secret, we put it in the input box and after submitting we are given the password for natas7.

```
jmxSiH3SP6Sonf8dv66ng8v1cIEdjXWr
```

## Level 7

### Access

http://natas7.natas.labs.overthewire.org/

username: natas7

password: jmxSiH3SP6Sonf8dv66ng8v1cIEdjXWr

### Password

Accessing the page, we can see two buttons, if we click either of them it is redirecting us to the same page, but an url parameter (`?page=home`). If we remove home leaving the complete url: http://natas7.natas.labs.overthewire.org/index.php?page= After loading, we can see the web is giving an error, because the file name can not be empty. This is telling us that the page parameter is the file name the server is opening, so following the comment found on the source code of the web, we put the page parameter to `/etc/natas_webpass/natas8`, being the complete url: http://natas7.natas.labs.overthewire.org/index.php?page=/etc/natas_webpass/natas8. After the web loads, the password for natas8 is showed.

```
a6bZCNYwdKqN5cGP11ZdtPg0iImQQhAB
```

## Level 8

### Access

http://natas8.natas.labs.overthewire.org/

username: natas8

password: a6bZCNYwdKqN5cGP11ZdtPg0iImQQhAB

### Password

For this challenge, we have to look at the source code, where we can see that the input send by the user, it is being transform by the function `encodeSecret` and compare with the variable named: `encodedSecret` which has a value of `3d3d516343746d4d6d6c315669563362`. So basically we need to undo the transformations in reverse order to the encoded Secret. 

In order, we will have to decode from hexadecimal, reverse the order of the string, and decode the base64. For doing this I will use CyberChef. On this [URL](https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')Reverse('Character')From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=M2QzZDUxNjM0Mzc0NmQ0ZDZkNmMzMTU2Njk1NjMzNjI) you can see the steps and the output: `oubWYf2kBq`. With this, we put it on the input box and after submitting, we get the password for natas9.

```
Sda6t0vkOPkM8YeOZkAGVhFoaplvlJFd
```

## Level 9

### Access

http://natas9.natas.labs.overthewire.org/

username: natas9

password: Sda6t0vkOPkM8YeOZkAGVhFoaplvlJFd

### Password

For this challenge we take a look at the source code to see what is going on. There we can see that the page is making a grep of the text entered in the textbox, which is passed to the server as a url parameter. Seeing that there are not sanitizing the text introduced, we can try making a grep of the file we want to read, where the password for natas10 is. With all of these, we introduce on the text field the following text: `-m 1 -e . /etc/natas_webpass/natas10` or we can go to the following url: [http://natas9.natas.labs.overthewire.org/index.php?needle=-m 1 -e . /etc/natas_webpass/natas10](http://natas9.natas.labs.overthewire.org/index.php?needle=-m%201%20-e%20.%20/etc/natas_webpass/natas10). I have put the `-m 1` in order to only show the first line of each file, the `-e .` is using regex for finding in the file, the regex of `.` is any character, the last part, is the file where we want to look. After loading the web page, we can see the first line of the files `dictionary.txt` and `natas10`. On this last one we are showed the password for natas10.

```
D44EcsFkLxPIkAAKLosx8z3hxX1Z4MCE
```

## Level 10

### Access

http://natas10.natas.labs.overthewire.org/

username: natas10

password: D44EcsFkLxPIkAAKLosx8z3hxX1Z4MCE

### Password

This challenge is a variation of the previews one, it adds a filter of some characters. It is looking for any of the following characters: `;|& `. Due to the way I made natas9, i did not used any of those characters. These means I can use the same input, modified to look for the password of natas11 with: `-m 1 -e . /etc/natas_webpass/natas11`. After putting it on the input box we obtain the password for natas11.

```
1KFqoJXi6hRaPluAmk8ESDW4fSysRoIg
```

## Level 11

### Access

http://natas11.natas.labs.overthewire.org/

username: natas11

password: 1KFqoJXi6hRaPluAmk8ESDW4fSysRoIg

### Password

In this challenge, we see on the code we have to modify the cookie in order to have the page show us the password. But the cookie has been scrambled with an xor and the codified in base64 and the key used in the xor, has been redacted, so we need to get it.

With all the information on the code, and with the value of the cookie, we have an input and output, so we can get the key of the xor.
- Input: `{"showpassword":"no","bgcolor":"#ffffff"}`
- Output: `MGw7JCQ5OC04PT8jOSpqdmkgJ25nbCorKCEkIzlscm5oKC4qLSgubjY=`
- Output decoded from Base64: `0l;$$98-8=?#9*jvi 'ngl*+(!$#9lrnh(.*-(.n6`

In order to get the key, we just need to make an xor of the *Input* and *Output decoded from Base64*. For this we cas use an online tool such us [this](https://xor.pw/#). We have to make sure the input type is set to ASCII. The output is the key used on the xor: `KNHLKNHLKNHLKNHLKNHLKNHLKNHLKNHLKNHLKNHLK`. We can check this by decoding the cookie, [here you can take a look](https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',false,false)XOR(%7B'option':'UTF8','string':'KNHLKNHLKNHLKNHLKNHLKNHLKNHLKNHLKNHLKNHLK'%7D,'Standard',false)&input=TUd3N0pDUTVPQzA0UFQ4ak9TcHFkbWtnSjI1bmJDb3JLQ0VrSXpsc2NtNW9LQzRxTFNndWJqWT0). After checking the passwords works, we can see that the secret used by the web is `KNHL`, that has been duplicated in order to have the same length of the input.

Now having the key, we can modify the cookie from: `{"showpassword":"no","bgcolor":"#ffffff"}` to `{"showpassword":"yes","bgcolor":"#ffffff"}`, then codify it [here](https://gchq.github.io/CyberChef/#recipe=XOR(%7B'option':'Latin1','string':'KNHL'%7D,'Standard',false)To_Base64('A-Za-z0-9%2B/%3D')&input=eyJzaG93cGFzc3dvcmQiOiJ5ZXMiLCJiZ2NvbG9yIjoiI2ZmZmZmZiJ9) and then change it on our browser setting its value to `MGw7JCQ5OC04PT8jOSpqdmk3LT9pYmouLC0nICQ8anZpbS4qLSguKmkz`. At last, we update the page and we get the password for natas12.

```
YWqo0pjpcXzSIl5NMAVxg12QxeC1w9QG
```

## Level 12

### Access

http://natas12.natas.labs.overthewire.org/

username: natas12

password: YWqo0pjpcXzSIl5NMAVxg12QxeC1w9QG

### Password

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
