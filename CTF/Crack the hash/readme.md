this one seems to be Ez one,so lets do it <br>

for the first 3 ones you need to do little search and copy pasting. <br>

the fourth one you need to know something first,the first 4 character of the hash,indicate that the hash is bcrypt ($2y$) and to know the value of it,you need to use the command of the **hashcat**,the command would be something simple but the options that u need are: <br>
  1- -m 3200 :telling the hashcat that use the bcrypt algorithm <br>
  2- -a 3 : meaning Mask attack,meaing I know something about the structure of the password, so don't try completely random possibilities <br>
  3- ?l?l?l?l :lowercase + lowercase + lowercase + lowercase,possible four-character lowercase passwords.<br>

  the command would be somehting like: <br>
  ```bash
hashcat -m 3200 -a 3 bcrypt.txt ?l?l?l?
```

