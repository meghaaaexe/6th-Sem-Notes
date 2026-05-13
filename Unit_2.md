## Number Theory

__Question__

Find multiplicative inverse  of 356 mod 45

__Solution :__ 

>u = u<sub>o</sub> -q.u<sub>1</sub>

repeat until r = 0

q|a|m|r|u<sub>o</sub>|u<sub>1</sub>|u|
|--|--|--|--|--|--|--|
7|356|45|41|1|0|1
10|41|4|1|1|-1|11
4|4|1|0|-1|11|

GCD = 1; u<sub>1</sub> = Multiplicative index = 11

356 X 11 mod 45 = 1

---

## Congruence Class

* A congruence class or residual class is a set of integers that are equivalent to each other modulo n

> a = (congruency symbol) b mod n
> (a-b) mod n = 0
>  a mod n = b mod n

* a and b gives same remainder when divided by n

__Question__

12 = 18 (mod 15)

__Solution__

12 mod 15 = 12
18 mod 15 = 3
This is invalid

---

__Question__

-3 = -18 (mod 15)
__Solution__
-3 mod 15 = 0 ; -18 mod 15 = 12
valid

__Question__

12 = -3(mod 15)
__Solution__
12 mod 15 = 12 ;-3 mod 15 = -3
valid

__Question__
7 = 19(mod 11)
__Solution__
7 mod 11 = 0; 19 mod 11 = 8
invalid

__Question__
4 = -19(mod11)
__Solution__
4 mod 11 = 0; -19 mod 11 = -8
invalid

__Question__
4 = -18 (mod 11)
__Solution__
4 mod 11 = 0; -18 mod 11 = -7
valid

__Question__
4<sup>-1</sup> = 2 mod 7
__Solution__
4<sup>-1</sup>mod 7 = ; 2 mod 7 = 0
1/4 = 2(mod 7)
valid

__Question__
Find if MI exists
2<sup>-1</sup> mod 10

__Solution__
> GCD (a,n) = 1
GCD of 2 and 10 is 2 so not valid

__Question__
2<sup>-1</sup> mod 11
__Solution__
GCD = 1 so GCD exists

__Question__
3<sup>-1</sup> mod 10
__Solution__
GCD exists

__Question__
Find MI of 9 mod 10 
__Solution__

q|a|m|r|u<sub>o</sub>|u<sub>1</sub>|u|
|--|--|--|--|--|--|--|



__Question__
Find MI of 23 in z<sub>100</sub>
__Solution__
u<sub>1</sub> = -13
-13 mod 100
100 + (-13)
87

__Question__
53 in z<sub>54</sub>
__Solution__

---

## Multiplicative Inverse Pair

Two numbers who are MI of each other

__Question__
Find MI pair for Z<sub>10</sub> and Z<sub>11</sub>
__Solution__
MI of 1 mod 10 = 1
MI of 2  mod 10 = 2
MI of  3 mod 10 = 3
MI of  4 mod 10 = 4
MI of  5 mod 10 = 5
MI of  6 mod 10 = 6
MI of 7  mod 10 = 7
MI of  8 mod 10 = 8
MI of  9 mod 10 = 9
MI of  10 mod 10 = 0

Z<sub>10</sub> = {(1,1), (3,7),(9,9),(7,3)}

Z<sub>11</sub> = 10 pairs

---

## Euler's Totient Function

> Z<sup>*</sup><sub>m</sub> = {0,...,m-1}

* Z<sub>m</sub> is the set of numbers that are relatively prime or co-prime with m in Z<sub>m</sub>
* Z<sup>*</sup><sub>m</sub> can be found out by knowing if GCD of m and other no. should be 1

* Z<sup>*</sup><sub>5</sub> = {1,2,3,4}

* phi (m) - ETF is denoted this way which gives the no. of elements in Z<sup>*</sup><sub>m</sub>

* phi(m) = |Z<sup>*</sup><sub>m</sub>| (cardinality)
* Z<sup>*</sup><sub>14</sub> = {1,3,5,9,11,13}, phi(Z14) = 6

### Conditions of phi (m)

* phi (p) = p-1 ; p=prime no.
* phi (p) = phi (mXn) = phi (m) X phi (n) ; m,n are co-prime
* phi (m) = phi (p<sup>e</sup>) = p<sup>e</sup> - p<sup>e-1</sup>

__Example__
* phi (16) = phi (2<sup>4</sup>) = 2<sup>4</sup> - 2<sup>3</sup> = 8
* phi(30) = 10
* phi(4) =
* phi(240) = 4

__Questions__

1. phi (27) = 3<sup>3</sup> = 3<sup>3</sup> - 3<sup>2</sup> = 18
2. phi(630) = phi(10) X phi( 63) = phi(5X2) X phi(9X7) = 1 X 4 X phi(3<sup>2</sup>) X 6 = 24 X (3<sup>2</sup>- 3<sup>1</sup>) = 24 X 6 = 144
3. phi(49) = 7<sup>2</sup> = 7<sup>2</sup> - 7<sup>1</sup> = 42
4. phi(1323) = 3<sup>3</sup> X 7<sup>2</sup>
5. phi(287375) = phi(6<sup>3</sup>) X phi(11) = 198000

---

## Fast Exponentiation Algorithm

> A<sup>B</sup> mod C

1. Convert B to binary value
2. Compute  __A<sup>i</sup> mod C__ using square method. Stop when __i < = B__

A<sup>1</sup> mod C = x
A<sup>2</sup> mod C = y
A<sup>4</sup> mod C
A<sup>8</sup> mod C ....

3. Find A<sup>B</sup> mod C using selective multiplication method
   
B = 5 = > 101 =
A<sup>5</sup> mod C
A<sup>101</sup> mod C
A<sup>4+1</sup> mod C

__Question__
11<sup>13</sup> mod 53
__solution__
13 - 1101 - 8+4+1
11<sup>1</sup> mod 53 = 11
11<sup>2</sup> mod 53 = ( 11 mod 53 X 11 mod 53) mod 53 = (11 X 11) mod 53 = 15
11<sup>4</sup> mod 53 = (11<sup>2</sup> mod 53 X 11<sup>2</sup> mod 53) mod 53 = (15 X 15) mod 53= 13
11<sup>8</sup> mod 53 = 10
11<sup>13</sup> mod 53 = 11<sup>8+4+1</sup> mod 53 = (11<sup>8</sup> mod 53 X 11<sup>4</sup> mod 53 X 11<sup>1</sup> mod 53 ) mod 53 = (10 X 13 X 11) = 52


__Question__
5 <sup>117</sup> mod 19
__solution__
117 - 1110101 - 5

5 mod 53 = 5
5<sup>2</sup> mod 19 = 5
5<sup>4</sup> mod 19 = 25<sup>2</sup> mod 19


__Questions__
15<sup>19</sup> mod 37
23<sup>971</sup> mod 503

---

## Fermat's Little Theorem

a is an integer, p is a prime no. If p dooes not divide a then a<sup> p-1</sup> $\equiv$ 1 (mod p)

2<sup>566</sup> $\equiv$ mod (567). Is it true?

p = 567, a = 2
567 is not prime. It is not true

Find 3<sup>-1</sup> (mod 31)

3<sup>30</sup> = 1 (mod 31) [Divide by 3]
3<sup>29</sup> = 1/3 (mod 31)
1/3 = 3<sup>29</sup> (mod 31)
3<sup>-1</sup>=3<sup>29</sup> (mod 31) 
3<sup>-16</sup> * 3<sup>8</sup> 3<sup>4</sup> 3(mod 31)

---

## Euler's Theorem

Let __a__ and __n__ be coprime numbers. phi(n) be the Euler's function. 
> a<sup>phi(n)</sup> $\equiv$ 1(mod n)


__Compute 6<sup>24</sup> mod 35__
a = 6; n = 35; a and n are coprime
phi(n) = phi(35) = phi(7 X 5) = 6 X 4 = 24
6<sup>24</sup> $\equiv$ 1 mod 35

__20<sup>62</sup> mod 77__
phi(n) = phi(77) = phi(11 X 7) = 10 X 6 = 60
20<sup>60</sup> mod 77
20<sup>60</sup> mod 77 X 20<sup>2</sup> mod 77
1 X 400 mod 77 = 15

__Compute 71<sup>-1</sup> mod 100 using Euler's theorem__

phi(100) = phi(25) X phi(4) = 40
71<sup>40</sup>  $\equiv$ 1 mod(100)
71<sup>-1</sup> mod 100 =  1/71 mod 100
71<sup>40</sup>  mod(100) / 71 mod 100
71<sup>40-1</sup>  mod(100) 
71<sup>39</sup>  mod(100) 

Use fast exponentiation to compute  71<sup>39</sup>  mod(100)

__8<sup>-1</sup>  mod(77)__

phi(77) = 60
8<sup>60</sup> $\equiv$ 1 mod(77)
8<sup>-1</sup>  mod (77) = 1/8 mod 77
8<sup>60</sup>  mod (77) / 8 mod 77
8<sup>60-1</sup>  mod (77) 
8<sup>59</sup>  mod (77) 
29

---

## Primitive Element

p is a prime no. and Z <sub>p</sub> = {0,1,2,3,.....,p-1}

> phi(p) = p-1 and a<sup>p-1</sup> $\equiv$ 1 mod (p)

Then a is said to be a primitive element in Z <sub>p</sub>



---
## Public Key Cryptography

* Public key / Two key / Asymmetric key
* Uses 2 keys :
*  Public - It can be known to anyone, is used to encrypt messages and verify signatures.
*  Private - It is only known to the recipient , used to decrypt messages and create signatures.
  
## Public Key Cryptosystems

> Z = E(KU<sub>b</sub>, E(KR<sub>a</sub>,X))
> X = D(KU<sub>a</sub>, D(KR<sub>b</sub>,Z))

* Public Key Cryptosystem (PKC) must be exercised 4 times
* It is used in digital signatures, key exchange, encryption/decryption
  
| Algorithm| Encryption/Decryption | Digital Signature| Key Exchange|
|--|--|--|--
| RSA |Yes|Y|Y
Eliptic Curve| Y|Y|Y
Diffie-Hellman|N|N|Y
Digital Signature System(DSS)| N|Y|N

## Requirements for PKC

* It is computationally easy for a party B to generate a pair
* For sender A
> C = E(KU<sub>b</sub>, M)
* For reciever B 
> M =  D(KR<sub>b</sub>, C) = D [KR<sub>b</sub>, E (KU<sub>b</sub>, M)]
* KU<sub>b</sub> - Public key, KR<sub>b</sub> - Private Key
> M =  D[KU<sub>b</sub>, E(KR<sub>b</sub>,M)] = D[KR<sub>b</sub>, E(KU<sub>b</sub>,M)]

* __Trap door one way function__ - easy to calculate in one direction but is computationally hard to do the inverse unless certain additional information is known.
* Example: Y = f(X) is easy but X = f<sup>-1</sup>(Y) is infeasible

## Misconceptions about PKC

* It replaces symmetric crypto - PKC complements private key crypto
* PKC is secure - no evidence found
* Key distribution is trivial - making something public is not trivial but easy

---

## RSA (Rivest, Shamir, Adelman) Algorithm

* It is the most widely used public key cryptography algorithm in the world.
* It can be used for both public key encryption and digital signatures.
* It makes use of prime numbers
* Integers used by RSA have to be large in size
* There are two sets of keys: private and public key


![alt text](image-2.png)

---

__Example Problem__

 P = 3, Q = 11 M = 14 C =?; C = 13 M = ?

n = 33
phi(n) = 2 X 10 = 20
Set of co-prime - Z<sup>*</sup><sub>n</sub> = {1,2,4,5,7,8,10,13,14,16,17,19,20..}
e = 7 (gcd should be 1 from above set of numbers)
d $\equiv$ e<sup>-1</sup> mod phi(n)
d = 7<sup>-1</sup> mod phi(20)
d = 3

Public Key - KU = {7,33}, Private Key - KR = {3,33}
Encryption:
Plain Text - M<n - 14<33
Cipher Text - C = 14<sup>7</sup> mod 33
C = 20


Decryption:
Cipher Text - 13
Plain Text - M = 13<sup>3</sup> mod 33
M = 19

---

## Digital Signatures using RSA

> D<sub>K Pvt </sub> (E <sub> K Pub </sub> (M) = M)

Text is encrypted using K <sub>Pvt</sub> and decrypted with <sub>K Pub</sub>

## Discrete Logarithm

> g<sup> x</sup> $\equiv$ h (mod p)

g is the primitive element in Z<sub>p</sub> and x is the Discrete Logarithm of h with base g mod p

x = dlog<sub>g,p</sub> (h)

__Example__

dlog<sub>g,p</sub> (1) = 0

---

## ElGamel Encryption Algorithm

* It is a public key cryptosystem which uses asymmetric key encryption
* It is based on difficulty of finding Discrete Logarithm
* It is the second category of PKC
  
* C1 carries the random exponent info required to compute the shared secret
* C2 contains the encryoted message

![alt text](image-3.png)
C2​=M⋅y<sup>r</sup>mod q

__Example__

Encrpyt message 10 using public key 9 and primitive root as 11 and a prime no. 23 also a random no. 3

q = 23, p=10, y= 9, r=3, G=11
C1 = 11 <sup> 3</sup> mod 23 = 20
C2 = (10.9 <sup>3</sup>) mod 23 = 22
P = [23 (20 <sup> 6</sup>)<sup>-1</sup>] mod 23 x = 6 (trial and error)
first 20 <sup> 6</sup> mod 23 = 16
22 X 16 <sup> -1 </sup> mod 23 = (22 X 16 <sup> -1 </sup> mod 23) mod 23
(22 X 13) mod 23 = 10


__Question__
 q=23,g=7, x=9, M=20, r=3

y = 7<sup>9</sup> mod 23 = 15
C1 = 7<sup>3</sup> mod 23 = 21
C2 = 20 (y<sup>3</sup> mod 23) = 18
p=[18(21<sup>9</sup>)<sup>-1</sup>] mod 23 = 

---

## Diffie Hellman(midsem)

* Diffie Hellman algorithm is used for key exchange mechanism to verify if a right key is shared by the right person.

* If a third party has identified a common secret, it would be still difficult to determine the private key

![alt text](image-4.png)

__Question__
P = 13, g = 6, a = 5, b = 4

A = 6<sup>5</sup> mod 13 = 2
B = 6<sup> 4</sup> mod 13 = 9
K<sub>a</sub> = 9<sup>5</sup> mod 13 = 3 = 6<sup> 20</sup> mod 13 = 
K<sub>b</sub> = 2<sup>4</sup> mod 13 = 3 = 6 <sup> 20</sup> mod 13 = 

