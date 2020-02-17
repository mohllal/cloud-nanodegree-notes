# Section 5: Authentication and Security

- One way hash algorithms:
  - bcrypt
  - scrypt
  - SHA-1
  - MD5

- ***Salt Rounds***: the password is passed through the salted hashing function, and the output is again passed through the hashing function in a loop. The more times we iterate on the hashing function, the more we can guard against brute force attacks that try to guess the password. The salt rounds decide how many times to go through this loop. Settings salt rounds to 10 means we iterate on this hashing function `2^10` times.

- In cryptography, a salt is random data that is used as an additional input to a one-way function that hashes data, a password or passphrase. Salts are used to safeguard passwords in storage. Historically a password was stored in plaintext on a system, but over time additional safeguards developed to protect a user's password against being read from the system. A salt is one of those methods.

- The salt value is generated at random and can be any length, in this case the salt value is 8 bytes long. The salt value is appended to the plaintext password and then the result is hashed, this is referred to as the hashed value.

- Common salt mistakes:
  - ***Salt reuse***: A fixed salt is when a programmer uses the same salt for every hashed password.
  - ***Short salt***: If a salt is too short, it will be easy for an attacker to create a rainbow table consisting of every possible salt appended to every likely password.

- A ***cryptographic hash function (CHF)*** is a hash function that is suitable for use in cryptography. It is a mathematical algorithm that maps data of arbitrary size (often called the "message") to a bit string of a fixed size (the "hash value", "hash", or "message digest") and is a ***one-way*** function, that is, a function which is practically infeasible to invert.

- In theoretical cryptography, the security level of a cryptographic hash function has been defined using the following properties:
  - ***Pre-image resistance***: Given a hash value h it should be difficult to find any message `m` such that `h = hash(m)`.
  - ***Second pre-image resistance***: Given an input `m1`, it should be difficult to find a different input `m2` such that `hash(m1)` = `hash(m2)`.
  - ***Collision resistance***: Implies *second pre-image resistance*, but does not imply *pre-image resistance*.

- A ***rainbow table*** is a precomputed table for reversing cryptographic hash functions, usually for cracking password hashes. Tables are usually used in recovering a password (or credit card numbers, etc.) up to a certain length consisting of a limited set of characters.