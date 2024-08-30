import random  
def asciicipher_encrypt(plaintext,jump):  
    encrypted_message=""  
    for x in range(len(plaintext)):  
        char= plaintext[x]  
  
        # Get the ASCII NUM of character  
        asciinum = ord(char)  
  
        # Jump the ASCII value within the printable ASCII range  
        new_ascii_num = ((asciinum - 32 + shift) % 95) + 32  
  
        # Convert back to a character and add to the encrypted message  
        encrypted_message += chr(new_ascii_num)  
  
  
    return encrypted_message  
def asciidecrypt(encrypted_message, shift):  
    decrypted_message = ""  
    for char in encrypted_message:  
        # Get the ASCII NUM of the character  
        ascii_num = ord(char)  
  
        # Reverse shift within the printable ASCII range  
        new_ascii_num = ((ascii_num - 32 - shift) % 95) + 32  
  
        # Convert back  character and add to the decrypted message  
        decrypted_message += chr(new_ascii_num)  
    return decrypted_message  
# Example  
message = "Hhjnesdjcjlds;kd34553@@!8@#$ 1mmcm"  
shift = random.randint(1, 94)  # Shift within the range [1, 94] (to avoid a shift of 0)  
encrypted_message = asciicipher_encrypt(message, shift)  
decrypted_message = asciidecrypt(encrypted_message, shift)  
  
print("Original message:", message)  
print("Shift:", shift)  
print("Encrypted message:", encrypted_message)  
print("Decrypted message:", decrypted_message)