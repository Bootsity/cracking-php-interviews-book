{book: true, sample: false}

# Chapter 12 - Security and Cryptography

#### Why do we need cryptography?

- Cryptography can be used for non-technological reasons like hiding physical messages, or creating ciphers so that only you and your friends can read your messages, but nowadays it is used for more vital reasons. It is the basis for Data Encryption. 
- Cryptography is used to make sure all of the things that I listed above shouldn't happen. I say shouldn't because nothing is perfect, and people can usually find loops holes or ways around the rules. Cryptography takes math and uses it to develop algorithms for computer systems to use to secure data either before data transfer or just for secure data storage.

#### What do we mean by hash functions?

A hash function is any function that can be used to map data of arbitrary size to data of a fixed size. The values returned by a hash function are called hash values, hash codes, digests, or simply hashes.

#### Whart is hash function in PHP?

It generates a hash value (message digest).

Syntax:

```php
string hash ( string $algo , string $data [, bool $raw_output = FALSE ] )
```

#### Example using hash().

```php
echo hash('ripemd160', 'The quick brown fox jumped over the lazy dog.');
```
Output:
```
ec457d0a974c48d5685a7efa03d137dc8bbde7e3
```

#### What is encoding and decoding?

Encoding means converting the message or information into a coded form in order to avoid hacking.

Decoding means converting signals into a different or usable form. The reverse process of encoding is known as decoding.

#### What is SHA1?

In cryptography, SHA-1, Secure Hash Algorithm-1 is a cryptographic hash function which takes an input and produces a 160-bit hash value known as a message digest – typically rendered as a hexadecimal number, 40 digits long.

The sha1() function uses the US Secure Hash Algorithm 1.

Example:

```php
$str = "Hello";
echo sha1($str);
```

Output:

```
f7ff9e8b7bb2e09b70935a5d785e0cc5d9d0abf0
```

#### Can sha1 be decrypted?

We cannot say that it is impossible at all (only in our world with limited resources it is). If you have a simple SHA1 hash, you could decrypt it if you guess what has been encrypted. But this is of course not efficient. In reality decrypting a large SHA-1 hash is nearly impossible.

#### What is sha1_file()?

The sha1_file() function calculates the SHA-1 hash of a file.
This function returns the calculated SHA-1 hash on success, or FALSE on failure.

```php
$filename = "test.txt";
$sha1file = sha1_file($filename);
echo $sha1file;
```

Output:
```
aaf4c61ddcc5e8a2dabede0f3b482cd9aea9434d
```

#### What are the disadvantages of sha1()?

Google announced the first SHA1 collision in 2017.
This requires a lot of computing power and resources. Since this never occurred naturally in real world under normal conditions we can rule out security risks today but not tomorrow.

SHA-1 for hashing passwords requires less computing power and this improves the performance of your application. Git still using SHA-1 for internal operations.

#### What MD5 means?

MD5 (technically called MD5 Message-Digest Algorithm) is a cryptographic hash function whose main purpose is to verify that a file has been unaltered.

The md5() function calculates the MD5 hash of a string.
The md5() function uses the RSA Data Security, Inc. MD5 Message-Digest Algorithm.

```php
$str = "Hello";
echo md5($str);
```

Output:
```
8b1a9953c4611296a827abf8c47804d7
```

#### Why can not a MD5 hash be decrypted?

There are no services which allow you to "decrypt MD5" because, MD5 is not an encryption algorithm. Hash functions take an input and create an output which cannot be turned back into the input. Because its not encrypted. MD5 is a hashing algorithm.

#### Is md5 reversible?

Now a days MD5 hashes or any other hashes for that matter are pre computed for all possible strings and stored for easy access. Though in theory MD5 is not reversible but using such databases you may find out which text resulted in a particular hash value. f(x) = 1 is irreversible. Hash functions aren't irreversible.

#### Compare sha1() and md5().

MD5 and SHA-1 have a lot in common; SHA-1 was clearly inspired on either MD5 or MD4, or both (SHA-1 is a patched version of SHA-0, which was published in 1993, while MD5 was described as a RFC in 1992).

The main structural differences are the following:

- SHA-1 has a larger state: 160 bits vs 128 bits.
- SHA-1 has more rounds: 80 vs 64.
- SHA-1 rounds have an extra bit rotation and the mixing of state words is slightly different (mostly to account for the fifth word).
- Bitwise combination functions and round constants are different.
- Bit rotation counts in SHA-1 are the same for all rounds, while in MD5 each round has its own rotation count.
- The message words are pre-processed in SHA-0 and SHA-1. In MD5, each round uses one of the 16 message words "as is"; in SHA-0, the 16 message words are expanded into 80 derived words with a sort of word-wise linear feedback shift register. SHA-1 furthermore adds a bit rotation to these word derivation.

#### What is enctype?

The enctype attribute specifies how the form-data should be encoded when submitting it to the server. The enctype attribute can be used only if `method="post"`

Following are different types of enctype.

- `application/x-www-form-urlencoded` is the default value if the enctype attribute is not specified. This is the correct option for the majority of simple HTML forms.

- `multipart/form-data` is necessary if your users are required to upload a file through the form.

- `text/plain` is a valid option, although it sends the data without any encoding at all. It is not recommended, as its behavior is difficult to predict.


#### Explain each Mcrypt function supported in PHP.

Mcrypt() supports many functions:

- Mcrypt_cbc()- Encrypts data in Cipher block chain mode.
- Mcrypt_cfb()- Encysrtpts data cipher feedback (CFB) mode
- Mcrypt_decrypt()- Decrypts data.
- mcrypt_encrypt- Encrypts plaintext with given parameters
- mcrypt_generic- encrypts data
- mcrypt_get_key_size - Get the key size of the specified cipher
- mdecrypt_generic – dectpyts data

#### What is cryptography authentication?

In cryptography, a message authentication code (MAC), sometimes known as a tag, is a short piece of information used to authenticate a message—in other words, to confirm that the message came from the stated sender (its authenticity) and has not been changed.