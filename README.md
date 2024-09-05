# Caesar Cipher Encryption and Decryption

def encrypt(text, shift):
    """
    This function takes a plaintext message and a shift value,
    and returns the encrypted message using Caesar Cipher.
    """
    result = ""
    
    # Traverse through each character of the message
    for i in range(len(text)):
        char = text[i]
        
        # Encrypt uppercase characters
        if char.isupper():
            result += chr((ord(char) + shift - 65) % 26 + 65)
        # Encrypt lowercase characters
        elif char.islower():
            result += chr((ord(char) + shift - 97) % 26 + 97)
        # Keep non-alphabet characters unchanged (e.g., spaces, punctuation)
        else:
            result += char
    
    return result

def decrypt(text, shift):
    """
    This function takes an encrypted message and a shift value,
    and returns the decrypted message using Caesar Cipher.
    """
    return encrypt(text, -shift)

def main():
    """
    Main function that drives the Caesar Cipher program.
    It prompts the user to select either encryption or decryption,
    and performs the operation accordingly.
    """
    print("Caesar Cipher Encryption/Decryption Tool")
    print("1. Encrypt the message: Hi I'm Sreeram K Y")
    print("2. Decrypt the message: Kl L'p Vuhuhdp N B")
    
    choice = input("Enter your choice (1 or 2): ")

    if choice == '1':
        # Encrypting the specific message "Hi I'm Sreeram K Y" with a shift of 3
        text = "Hi my name is Suhaib"
        shift = 3
        encrypted_text = encrypt(text, shift)
        print(f"Encrypted message: {encrypted_text}")
    elif choice == '2':
        # Decrypting the encrypted message with a shift of 3
        text = "Kl L'p Vuhuhdp N B"
        shift = 3
        decrypted_text = decrypt(text, shift)
        print(f"Decrypted message: {decrypted_text}")
    else:
        print("Invalid choice. Please enter 1 for encryption or 2 for decryption.")

if __name__ == "__main__":
    main()
