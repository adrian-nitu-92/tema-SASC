# S-Box Modifications and Their Effect in DES-like Encryption Systems #

The most basic method of cryptanalysis is the exhaustive search method, also
known as the brute force and known plaintext attack. This method uses merely one
block of known plaintext and the resultant ciphertext to find the secret key. With
this pair of known plaintext/ciphertext, it could take 2^56 maximum DES calculations
to find the correct secret key in DES encryption. With today’s processing power
this not only is possible; indeed it has been performed time and time again. See [4], [5].

## Basic idea ##

Haphazardly changing the order of the s-boxes is not safe, yet the ordering in
DES is not optimized for all attacks as it is defined. By analyzing all possible
orders (8!), Biham and Biryukov[3] found the best one, most resistant to the above
attacks: S2, S4, S6, S7, S3, S1, S5, and S8. This order does not provide much
additional protection against differential cryptanalysis, but it does have a
significant improvement against exhaustive search method, linear cryptanalysis
and the improved Davies’ Attack.

## Usage Example ##

```python
data = "Data to be encrypted"
k = des("DESCRYPT", CBC, "\0\0\0\0\0\0\0\0", pad=None, padmode=PAD_PKCS5)
print "Encrypted: %r" % d
print "Decrypted: %r" % k.decrypt(d)
assert k.decrypt(d, padmode=PAD_PKCS5) == data

```

## References ##

1. https://www.sans.org/reading-room/whitepapers/vpns/s-box-modifications-effect-des-like-encryption-systems-768
2. http://twhiteman.netfirms.com/des.html
3. https://www.iacr.org/cryptodb/data/paper.php?pubkey=85
4. https://ireland.emc.com/emc-plus/rsa-labs/standards-initiatives/has-des-been-broken.htm
5. https://ireland.emc.com/emc-plus/rsa-labs/standards-initiatives/what-is-the-rsa-secret-key-challenge.htm
