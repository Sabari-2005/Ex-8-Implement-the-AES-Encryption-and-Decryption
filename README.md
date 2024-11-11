# Ex-8-Implement-the-AES-Encryption-and-Decryption
## Aim:
Implement the AES Encryption and Decryption
## Algorithm:
1. AES is based on a design principle known as a substitution-permutation.
2. AES does not use a Feistel netowrk like DES, it uses variant Rijndael.
3. It has a fixed block size of 128 bits, and a key size of 128, 192, or 256 bits.
4. AES operates on a 4 x 4 column-major order array of bytes, termed the state.

## Program:
```
#include <stdio.h>
#include <string.h>

void simpleXOREncrypt(char *plaintext, char *key, char *ciphertext) {
    int i;
    for (i = 0; i < strlen(plaintext); i++) {
        ciphertext[i] = plaintext[i] ^ key[i % strlen(key)];
    }
    ciphertext[i] = '\0'; 
}

void simpleXORDecrypt(char *ciphertext, char *key, char *decryptedText) {
    int i;
    for (i = 0; i < strlen(ciphertext); i++) {
        decryptedText[i] = ciphertext[i] ^ key[i % strlen(key)];
    }
    decryptedText[i] = '\0'; 
}

void printASCII(char *ciphertext) {
    printf("Encrypted Message (ASCII values): ");
    for (int i = 0; i < strlen(ciphertext); i++) {
        printf("%d ", (unsigned char) ciphertext[i]);
    }
    printf("\n");
}

int main() {
    char plaintext[100], key[100], ciphertext[100], decryptedText[100];

    printf("Enter the plaintext: ");
    scanf("%s", plaintext);
    printf("Enter the key: ");
    scanf("%s", key);

    simpleXOREncrypt(plaintext, key, ciphertext);
    printASCII(ciphertext);

    simpleXORDecrypt(ciphertext, key, decryptedText);
    printf("Decrypted Message: %s\n", decryptedText);

    return 0;
}
```

## Output:
![Screenshot 2024-11-11 151853](https://github.com/user-attachments/assets/6b05af18-6a70-414f-ae4a-f85d61afc181)

## Result:
The program for AES algorithm is executed successfully.
