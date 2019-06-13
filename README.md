## Generate SSH Key in WINDOWS

###### Generate public/private rsa key pair
```
~/.ssh$ ssh-keygen -t rsa -b 4096 -C "<username here>"
Generating public/private rsa key pair.
Enter file in which to save the key (/c/Users/Naresh/.ssh/id_rsa): id_rsa_git_nseepana
Enter passphrase (empty for no passphrase):
Enter same passphrase again:
Your identification has been saved in id_rsa_git_nseepana.
Your public key has been saved in id_rsa_git_nseepana.pub.
The key fingerprint is:SHA256:szvaQmV4kwHpggW/d8yzGen6niaQhgrvVGi3TY4SJH0 <username here>
The key's randomart image is:
+---[RSA 4096]----+
|.o         .  .  |
|o . E   *  . .o. |
|o  .     .  .    |
|+.      +   .=ooo|
|o+  E  +S . . .=+|
|. +.. o. . .  o =|
| . .o+. o . .  o |
|    .o..E. . o.  |
|    .oooo.  +o   |
+----[SHA256]-----+
```
###### If you created key other than id_rsa name add key to ssh agent
```
~/.ssh$ ssh-add ./id_rsa_git_nseepana
Enter passphrase for ./id_rsa_git_nseepana:
Identity added: ./id_rsa_git_nseepana (./id_rsa_git_nseepana)
```
###### To copy public key
```
~/.ssh$ clip < ./id_rsa_git_nseepana.pub
```

###### To clear cache 
```
~/.ssh$ ssh-add -D
All identities removed.
```

###### To list .pub files
```
 ~/.ssh$ clip < ~/.ssh/id_rsa.pub
```

###### To identify id_rsa where its assigned it to
```
~/.ssh$ ssh -T -ai ~/.ssh/id_rsa git@github.com
Warning: Permanently added the RSA host key for IP address '<ip address here>' to the list of known hosts.
Hi nseepana! You've successfully authenticated, but GitHub does not provide shell access.
```
