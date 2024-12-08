    Cybersecurity
Module 10 Challenge Submission File


Cryptography Challenge: Ransomware Riddles

Make a copy of this document to work in, and then for each mission, add the solution below the prompt. Save and submit this completed file as your Challenge deliverable.


Ransomware Riddles

Riddle 1:

Password: gruber

Key: 6skd8s

I actually built a python script to encode/decode caesar ciphers:
alphabet = ["a", "b", "c", "d", "e", "f", "g", "h", "i", "j", "k", "l", "m", "n", "o", "p", "q", "r", "s", "t", "u", "v", "w", "x", "y", "z"]

def caeser_algorithm(amount, text):
    cipher_text = ''
    for letter in text:
        if letter == " ":
            cipher_text += letter
        else:
            cipher_text += alphabet[(alphabet.index(letter) + amount) % len(alphabet)]
    return cipher_text
    # this is all there is to it: letter + shift amount, modulo alphabet size. deciphering just flips + to -

def run(): 
    print("Hello! Let's pretend we're back in 50 BCE and work with Caeser Ciphers!")
    encode_check = int(input("Before we start, I gotta know: are we encoding (1) or decoding (2) a cipher? \n"))
    if encode_check == 1:
        word = 'encode'
        direction = 1
        brute_check = 'n'
    elif encode_check == 2:
        word = 'decode'
        direction = -1
        brute_check = input('Deciphering, huh? Do I need to brute force this?\nYes or No: ').lower()
    text = input('Enter the message you want me to {0}.\n'.format(word)).lower()
    if 'y' in brute_check:
        print('Starting with {0}.'.format(text))
        for place, letter in enumerate(alphabet):
            print('Testing if a is shifted to {0}...'.format(letter))
            print('Result: {0}'.format(caeser_algorithm(place * direction, text)))
    else:
        amount = int(input('How many places should I move the letters? Enter a number between 1 and 25.\n'))
        print("Okay! Here's your result:")
        print('Original: {0}\nNew: {1}'.format(text, caeser_algorithm(amount * direction, text)))


if __name__ == "__main__":
    # this is boilerplate in case you try to throw this in other projects, don't worry about it
    run()





Riddle 2:

Password: Gennero
Key: cy8snd2


Riddle 3:

Password: takagi
Key: ud6s98n


Riddle 4:

Password Questions:
Jill’s Public Key
Jill’s Private Key
12 Asymmetric and 15 Symmetric
Alice’s Public Key
Key: 7gsn3nd2




Riddle 5:

Password: argyle
Key: ajy39d2


Riddle 6:

Password: mcclane
Key: 7skahd6


Ransomware Screenshot

Include a screenshot showing proof that you’ve decrypted the ransomware:






© 2022 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
