from Crypto.PublicKey import RSA  
from Crypto.Cipher import PKCS1_OAEP  
  
  
# Function to encrypt a message using RSA  
def rsaencrypt(plaintext, public_key):  
    cipher = PKCS1_OAEP.new(public_key)  
    ciphertext = cipher.encrypt(plaintext.encode())  
    return ciphertext  
  
  
# Function to decrypt a message using RSA  
def rsadecrypt(ciphertext, private_key):  
    cipher = PKCS1_OAEP.new(private_key)  
    plaintext = cipher.decrypt(ciphertext)  
    return plaintext.decode()  
  
  
# Example usage  
if __name__ == "__main__":  
    # Generate RSA keys  
    key = RSA.generate(2048)  
    private_key = key  
    public_key = key.publickey()  
  
    message = "dghghhkjl@$%^^hjj kkkjSDGHJJ"  
  
    # Encrypt  message  
    encrypted_message = rsaencrypt(message, public_key)  
    print("Encrypted message:", encrypted_message)  
  
    # Decrypt message  
    decrypted_message = rsadecrypt(encrypted_message, private_key)  
    print("Decrypted message:", decrypted_message)
    
AES ENCRYPTION
from Crypto.PublicKey import RSA
from Crypto.Cipher import PKCS1_OAEP

# Function to encrypt a message using RSA
def rsa_encrypt(plaintext, public_key):
    cipher = PKCS1_OAEP.new(public_key)
    ciphertext = cipher.encrypt(plaintext.encode())
    return ciphertext

# Function to decrypt a message using RSA
def rsa_decrypt(ciphertext, private_key):
    cipher = PKCS1_OAEP.new(private_key)
    plaintext = cipher.decrypt(ciphertext)
    return plaintext.decode()

# Example usage
if __name__ == "__main__":
    # Generate RSA keys
    key = RSA.generate(2048)
    private_key = key
    public_key = key.publickey()

    message = "fjcgkhhvgjfhhxfed@#$%^&SFHJJ"
    
    # Encrypt the message
    encrypted_message = rsa_encrypt(message, public_key)
    print("Encrypted message:", encrypted_message)

    # Decrypt the message
    decrypted_message = rsa_decrypt(encrypted_message, private_key)
    print("Decrypted message:", decrypted_message)
