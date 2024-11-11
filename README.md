# EX-NO-10-Diffie-Hellman-Key-Exchange-Algorithm

## AIM:
To Implement Diffie Hellman Key Exchange Algorithm 

## Algorithm:

1. Diffie-Hellman Key Exchange is used for securely sharing a secret key between two parties over an insecure channel.

2. Initialization: Agree on a large prime number \( p \) and a primitive root \( g \) modulo \( p \) (both are public values).

3. Key Exchange Process: 
   - Each party selects a private key and calculates their public key using the formula \( g^{\text{private key}} \mod p \).
   - Each party then shares their public key with the other.

4. Secret Key Computation: 
   - Each party computes the shared secret key using the received public key and their own private key.

5. Security: The difficulty of computing discrete logarithms ensures that the shared key remains secure even if public values are intercepted.

## Program:
```c
#include <stdio.h>  
#include <math.h>  
// Function to calculate power (a^b % P)  
long long int power(long long int a, long long int b, long long int P) {     
if (b == 1)         
return a;     else  
return ((long long int)pow(a, b) % P);  
}  
int main() {  
long long int P, G, x, a, y, b, ka, kb;  
// Both the users will be agreed upon the public keys P and G     
P = 23; // A prime number P is taken     printf("The value of P: 
%lld\n", P);  
G = 9; // A primitive root for P, G is taken     
printf("The value of G: %lld\n\n", G);  
// Alice will choose the private key a     a = 4; // a is 
the private key chosen by Alice (random)     printf("The 
private key a for Alice: %lld\n", a);  
x = power(G, a, P); // gets the generated key     
printf("The public key x for Alice: %lld\n\n", x);  
// Bob will choose the private key b  
b = 3; // b is the private key chosen by Bob (random)     
printf("The private key b for Bob: %lld\n", b);  
y = power(G, b, P); // gets the generated key     
printf("The public key y for Bob: %lld\n\n", y);  
// Generating the secret key after the exchange of keys     
ka = power(y, a, P); // Secret key for Alice     kb = 
power(x, b, P); // Secret key for Bob  
printf("Secret key for Alice is: %lld\n", ka);     
printf("Secret key for Bob is: %lld\n", kb);  
return 0;  
} 
```

## Output:
![Screenshot 2024-10-18 140556](https://github.com/user-attachments/assets/43f18ef3-0698-4ff5-a796-561793e3ff40)



## Result:
  The program is executed successfully

