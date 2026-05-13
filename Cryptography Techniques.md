# Chapter - 2
# Classical Crytography Techniques

__Some common terminologies__

* __Plain Text__ -  The original message or data that is fed into the
algorithm as input.

* __Cipher Text__ - This is the scrambled message produced as output. It depends on the plaintext and the secret key. 

* __Cryptography__ - The science of securing information by transforming it into unreadable ciphertext 
  
* __Crypt Analysis__ - Method of deciphering w/o knowing the key
  
* __Cryptology__ - Combination of cryptology and crypto analysis
  
---

### Types of cryptography

3 types based on __operation__

![alt text](image.png){width:500 height:100} 


1) __Substitution Cypher__ 

* Letters of plain text is replaced by letters, numbers or symbols.
* Caesar Cypher is a popular substitution cipher.
* a,b,c,...,z == > 0,1,2,...,25
*  Encryption formula
* > C = (P + K) (mod 26)  
  > P - Plain text value, K - Shift key
* Decryption formula
* > P = (C - K) (mod 26)

2) __Transposition Cipher__
3) __Product Cipher__

2 types based on __number of keys__
1) __Single key__ / __Private Key__ / __Symmetric Key__
2) __Two keys__ / __Public Key__ / __Asymmetric Key__

2 types on size of __plain text__
1) __Block__
2) __Stream__

---

## Play-Fair Cipher

### Rules

5X5 matrix for the word CRYPTOGRAPHY

| C|R|Y|P|T
|--|--|--|--|--|
O|G|A|H|B|
D|E |F|I|K|
L|M|N|Q|S|
U|V|W|X|Z|

* Place the letters one by one in the 5X5 matrix.
* It has 25! possible keys (if keys are not repeated) i.e. 2<sup>84</sup> and if keys are identical then 2<sup>79</sup>
* After all the letters of the word is filled, place the letters in alphabetical order.
* Do not repeat any letters.
* If letters of a pair are same, then add X,Y or Z in between those letters.
* If letters appear on the same colomn, replace them with the letters immediate below with wrapping.
* If letters appear on the same row, replace them with the letter to the immediate right with wrapping (according to the direction)
* If letters are not on the same row or colomn, replace them with the letters on the same row respectively but at the other pair of corners of a rectangle by the original pair.

---

__Question 1__

Key - __"Cryptography class spring"__
 Plain text- __"Hello find the solution"__

*Answer:*

|C|R|Y|P|T|
|--|--|--|--|--|
|O|G|A|H|L|
|S|I|N|B|D|
E|F|K|M|Q|
|U|V|W|X|Z

* Plain text pairs : HE LX LO FI ND TH ES OL UT IO NZ
* Cipher Text pairs: OM HZ GA VR BS PL UC GA CZ SG DW
___

__Question 2__

Key - __"Keyword"__
Plain text - __"Why don't you"__, __"Come to the window"__, __"The big wheel"__

*Answer:*

|K|E|Y|W|O|
|--|--|--|--|--|
R|D|A|B|C|F
G|H|I|K|L
M|N|P|Q|S|
T|U|V|X|Z

WH YD ON TY OU \
EK EA ES VK EZ

CO ME TO TH EW IN DO WX \
TH EB IG WH EE LX

TH EB IG WH EX EL \
UG WD KL EK WU OH
___

__Question 3__

Key - __"Monarchy"__
Plain text - __"I am at college right now"__

|M|O|N|A|R|
|--|--|--|--|--|
C|H|Y|B|D|
E|F|G|I|K
L|P|Q|S|T
U|V|W|X|Z

IA MA TC OL LE GE RI GH TN OW \
BS OR LD MP UL IF AK FY QR NV

---

## Polyalphabetic Cipher

* This is another approach to improve security by using multiple cipher alphabets called as polyalphabetic substitution cipher.
* It repeats the key from the beginning once after the end of the key is reached.
* The simplest cipher under this is Vigenere Cipher which is effectively multiple ceaser ciphers.
* The key is multiple letters long.
* Decryption in Vigenere Cipher simply works in reverse.
* The same plain text charecter is encrpted to different.

__k = k1 k2 .... kd__

|Key| Plain Text | Cipher Text|
|--|--|--|
C A T C A T C| C O L L E G E| E O E N E Z G|
2 0 19 2 0 19 2| 2 14 11 11 4 6 4

---

__Question 1__

Key - __D E C E P T I V E__
Plain Text - __"We are discovered, save yourself"__

D E C E P  T  I  V  E
3 4 2 4 15 19 8  21 4


Cipher Text - Z I C V T W Q N G R Z G V T W A V Z H C Q L G L M G J 


|A| B| C| D| E| F| G| H| I| J| K|
|--|--|-|-|-|-|-|-|-|-|-|
|0 |1| 2| 3| 4| 5| 6| 7| 8| 9| 10|


|L|  M|  N|  O|  P|  Q|  R|  S|  T|  U|  
|-|-|-|-|-|-|-|-|-|-
|11 |12|  13| 14| 15 |16 |17 |18 |19 |20 |

|V|  W|  X|  Y|  Z|
|-|-|-|-|-|
|21 |22 |23 |24 |25|

---

## Security of Vigenere Cipher

* If a Vigenere Cipher is suspected, then determine the length of the keyword
* If two identical sequences of a plain text letters occur at a distance, i.e an integer multiple of the keyword length, which generates identical cipher text sequences. 
* To find a solution against the know frequency using the repeated key, another approach called Auto Key System can be used.
* In Auto Key System  a keyword is concantenated with the plain text to provide a running key.
* Consider the encryption according to the order of the plain text.


## Vernam Pad

> Encryption
> C<sub>i</sub> = (p<sub>i</sub> + k<sub>i</sub>) (mod 26)
> Decryption
> p<sub>i</sub> = (C<sub>i</sub> - k<sub>i</sub>) (mod 26)

__C<sub>i</sub> = P<sub>i</sub> XOR k<sub>i</sub>__

|X|0|R|
|--|--|--|
0|0|0
0|1|1
1|0|1
1|1|0

__ASCII Value__
(A - Z) = (65 - 90)
(a - z) = (97 - 122)

---

__Question 1__

Plain Text - C A T
Key - A A A 

__Solution__

ASCII - C A T = 676584
Binary - 01000011 01000001 01010100

ASCII - A A A = 656565
Binary - 01000001 01000001 01000001

__C<sub>i</sub> = P<sub>i</sub> XOR k<sub>i</sub>__
C<sub>i</sub> =  01000011 01000001 01010100 + 01000001 01000001 01000001
    C<sub>i</sub>       = 00000011 00000000 01010101
    C<sub>i</sub> = 2021


* In theory it is 100% secure
* __C<sub>i</sub> = P<sub>i</sub> XOR k<sub>i</sub>__
* Key lengh has to be equal to the plain text length and should be purely random (generated from nature). 
* Random keys are pure random keys that cannot be genrated by a computer.

---

## Transposition / Permutation Cipher

These hide messages by rearranging the letter order w/o altering the actual lettrs used.


1. __Rail Fence Cipher__ 
   * Write message letters out diagonally over a no. of rows and then read off cipher row by row.
   * Do not fill empty spaces.
   * eg : "meet me after the toga party"  
  m e m a t r h t g p r y
e t e f e t e o a a t
     Cipher Text  : MEMATRHTGPRYETEFETEOAAT 

2. __Columnar Transposition Cipher__

* Plain Text - "Attack postponed until 2am" 
* Key = 4 3 2 1 5 6 7
* Take the least key value column
* C.T - aptm ttna tsuo aodw coix knly petz
* This is column wise transposition
  
| 4 |3 |2 |1 |5 |6| 7| 
|--|--|--|--|--|--|--|
| a| t| t| a|c|k|p|
|o|s|t|p|o|n|e|
d|u|n|t|i|l|t|
w|o|a|m|x|y|z|

* For row wise transposition

4|a|o|d|
|--|--|--|--
3|t|s|u|
2|t|t|n|
1|a|p|t|
5|c|o|i|
6|k|n|l|
7|p|e|a|

---

## Rotor Machine

* It is an electro mechanical encryption device that encrypts letters by passing them through a set of rotating discs called rotors.
* It changes location after every key press.
* Rotors are connected internally w the help of wires
* It was used in world war 2 which was popularly known as enigma

---

## Steganography

* It is the technique of hiding secret info inside another file so that no one knows a message exits.
* __Types__ : Image, audio, video and text

---

__Question__

Find the PT and key for given cipher text
YMJGTTPLFIXGDGDJWSJXYANSHJSYBWNLMYITJXSTYHTSYFNSYMJQJYYJWJ

__Solution__

Keep trying with different key values for few letters until it makes sense

By trial and error method to find k value
if k = 1
Y = (P-1) (mod 26) = Z; M = N; J = K; G = H

if k = 2
Y = A; M = O; J = L; G = J

Shift key is 5 (reverse alphabetic order)


---

__Question__


P.T is "abccab" has been encrypted with Vignere cipher and the  cipher text is "bbccab". What is the key length?

__Solution__

|a|b|c|c|a|b|
|--|--|--|--|--|--|
|b|b|c|c|a|b|

Here, there are 5 matching columns. Counting the number of displaced columns, from beginning to the end of the matching column, answer is 6.

---

__Question__

20 17 13 9 7 16 15 18 11 2 10 12 1 14 5 19 4 6 3 8
encrypt the message using transposition technique " Markworth attacked by two persuit planes"

__solution__

