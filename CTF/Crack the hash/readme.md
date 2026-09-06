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
be pacient with the process,it can take some time to give you the result.<br>

Meanwhile lets to a review: <br>
A password hash is designed to be a one-way function. This means that if we have the hash of a password, we cannot simply reverse the hash to obtain the original password.

Instead, if an attacker obtains a password hash, they can attempt to discover the original password by guessing possible passwords.

The process is essentially:

Take a possible password.
Hash it using the same hashing algorithm.
Compare the resulting hash with the stolen hash.
If the hashes match, the guessed password is likely the original password.
If they don't match, try another candidate.

For example:

Candidate password
        ↓
     Hash it
        ↓
Compare with
target hash
        ↓
   ┌────┴────┐
   ↓         ↓
 Match     No match
   ↓         ↓
Password   Try another
 found     password

Tools such as Hashcat automate this process by testing large numbers of candidate passwords.

This is why password strength and slow password-hashing algorithms such as bcrypt are important: the stronger the password and the more computationally expensive the hashing algorithm, the harder it is to successfully guess the original password.

Important: Hash cracking is not the same as decrypting a password hash. You are not reversing the hash; you are testing guesses until one produces the same hash.

