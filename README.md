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
```
#include <stdio.h>
#include <math.h>

// Function to perform modular exponentiation
long int power(long int a, long int b, long int p)
{
    long int result = 1;
    int i;

    for (i = 1; i <= b; i++)
        result = (result * a) % p;

    return result;
}

int main()
{
    long int p, g;
    long int a, b;
    long int A, B;
    long int keyA, keyB;

    // Input values
    printf("Enter the value of p (prime number): ");
    scanf("%ld", &p);

    printf("Enter the value of g (primitive root): ");
    scanf("%ld", &g);

    printf("Enter private key for User A: ");
    scanf("%ld", &a);

    printf("Enter private key for User B: ");
    scanf("%ld", &b);

    // Calculate public keys
    A = power(g, a, p);
    B = power(g, b, p);

    // Calculate secret keys
    keyA = power(B, a, p);
    keyB = power(A, b, p);

    // Display results
    printf("\nPublic Key of A: %ld", A);
    printf("\nPublic Key of B: %ld", B);

    printf("\nSecret Key calculated by A: %ld", keyA);
    printf("\nSecret Key calculated by B: %ld", keyB);

    return 0;
}

```



## Output:

![590ce911-7b06-4cc8-aa5b-3828fba0cd5f](https://github.com/user-attachments/assets/085b755f-378d-43b0-b252-993e9c1c07e1)


## Result:
  The program is executed successfully

