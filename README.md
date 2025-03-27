# CRYPTOGRAPHY
HILL CIPHER
# EX. NO: 1(C) AIM:
IMPLEMENTATION OF HILL CIPHER
 
## To write a C program to implement the hill cipher substitution techniques.

## DESCRIPTION:

Each letter is represented by a number modulo 26. Often the simple scheme A = 0, B
= 1... Z = 25, is used, but this is not an essential feature of the cipher. To encrypt a message, each block of n letters is  multiplied by an invertible n × n matrix, against modulus 26. To
decrypt the message, each block is multiplied by the inverse of the m trix used for
 
encryption. The matrix used
 
for encryption is the cipher key, and it sho
 
ld be chosen
 
randomly from the set of invertible n × n matrices (modulo 26).


## ALGORITHM:
```
STEP-1: Read the plain text and key from the user. STEP-2: Split the plain text into groups of length three. STEP-3: Arrange the keyword in a 3*3 matrix.
STEP-4: Multiply the two matrices to obtain the cipher text of length three.
STEP-5: Combine all these groups to get the complete cipher text.
```
## PROGRAM 
```
import numpy as np

def hill_cipher_encrypt_decrypt():
    a = np.array([[6, 24, 1], [13, 16, 10], [20, 17, 15]])  # Encryption key matrix
    b = np.array([[8, 5, 10], [21, 8, 21], [21, 12, 8]])   # Decryption key matrix
    
    msg = input("Enter plain text (3 characters): ").upper()
    if len(msg) != 3:
        print("Error: Please enter exactly 3 characters.")
        return
    
    c = np.array([ord(char) - 65 for char in msg])  # Convert to numerical values
    print("Plaintext Numerical Values:", c)
    
    # Encryption
    d = np.dot(a, c) % 26  # Multiply and mod 26
    encrypted_text = ''.join(chr(num + 65) for num in d)
    print("Encrypted Cipher Text:", encrypted_text)
    
    # Decryption
    decrypted_values = np.dot(b, d) % 26
    decrypted_text = ''.join(chr(num + 65) for num in decrypted_values)
    print("Decrypted Cipher Text:", decrypted_text)

if __name__ == "__main__":
    hill_cipher_encrypt_decrypt()

```
## OUTPUT
![WhatsApp Image 2025-03-27 at 09 17 59_94e9d838](https://github.com/user-attachments/assets/7a7efc6f-969b-4467-af0b-1121275ca225)

## RESULT
The program Hill cipher is successfully implented.
