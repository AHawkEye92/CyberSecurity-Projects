import random  
def cesarcipher_encrypt(plaintext,jump):  
    encrypted_message=""  
    for x in range(len(plaintext)):  
        char= plaintext[x]  
        if char.isupper():  
            # Checking the character is uppercase letter  
            position = ord(char) - ord('A')  
            # Perform the jump  
            new_place = (position + jump) % 26  
            # Convert back to character  
            new_char = chr(new_place + ord('A'))  
            encrypted_message += new_char  
        elif char.islower():  
  
            position = ord(char) - ord('a')  
            # Perform the jump  
            new_place = (position + jump) % 26  
            # Convert back to character  
            new_char = chr(new_place + ord('a'))  
            encrypted_message += new_char  
        else:  
            # If not a letter, don't change    
encrypted_message += char  
    return encrypted_message  
def cesar_decrypt(encrypted_text, jump):  
    return cesarcipher_encrypt(encrypted_text, -jump)  
  EXAMPLE:
message = "po6cLPOC54H8O!"  
jump = random.randint(0, 25)  
encryptedmsg = cesarcipher_encrypt(message, jump)  
decryptedmsg = cesar_decrypt(encryptedmsg, jump)  
print("message encrpted=",encryptedmsg)  
print("message decrpted=",decryptedmsg)

OUTPUT
message encrpted= xw6kTXWK54P8W!
message decrpted= po6cLPOC54H8O!