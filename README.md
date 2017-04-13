# tema-SASC

Base idea:

Haphazardly changing the order of the s-boxes is not safe, yet the ordering in
DES is not optimized for all attacks as it is defined. By analyzing all possible
orders (8!), Biham and Biryukov found best one, most resistant to the above
attacks: S2, S4, S6, S7, S3, S1, S5, and S8. This order does not provide much
additional protection against differential cryptanalysis, but it does have a
significant improvement against linear cryptanalysis and the improved Davies’
Attack

