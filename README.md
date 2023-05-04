# github
github module 10 

import string
import sys

def caesar_cipher(message, shift):
    alphabet = string.ascii_uppercase
    encrypted_message = ""
    for char in message:
        if char.upper() in alphabet:
            idx = (alphabet.index(char.upper()) + shift) % len(alphabet)
            encrypted_message += alphabet[idx]
    return encrypted_message

if __name__ == "__main__":
    shift = int(sys.argv[1])
    message = input("Enter the message to encrypt: ")
    encrypted_message = caesar_cipher(message, shift)
    for i in range(0, len(encrypted_message), 5):
        print(encrypted_message[i:i+5], end=" ")
        if (i + 1) % 50 == 0:
            print()
