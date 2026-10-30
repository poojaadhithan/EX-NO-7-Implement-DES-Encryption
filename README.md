# EX-NO-7-Implement-DES-Encryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:
```
#include <stdio.h>
#include <string.h>

void xorCrypt(char input[], char key[], char output[], int len)
{
    int keyLen = strlen(key);

    for (int i = 0; i < len; i++)
        output[i] = input[i] ^ key[i % keyLen];

    output[len] = '\0';
}

int main()
{
    char key[] = "ABC";
    char msg[] = "POOJA";
    char enc[100], dec[100];

    int len = strlen(msg);

    printf("Name: %s\n", msg);

    xorCrypt(msg, key, enc, len);

    printf("Encrypted: ");
    for (int i = 0; i < len; i++)
        printf("%02X ", (unsigned char)enc[i]);

    xorCrypt(enc, key, dec, len);

    printf("\nDecrypted: %s\n", dec);

    return 0;
}
```


## Output:
<img width="1920" height="1080" alt="Screenshot (88)" src="https://github.com/user-attachments/assets/63e96ba3-bb10-425e-8074-442814f150f9" />


## Result:
  The program is executed successfully

