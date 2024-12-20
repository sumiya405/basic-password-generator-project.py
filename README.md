# basic-password-generator-project.py
***
import random
import string
def generate_password():
    print('\n---password generated--')
    try:
        length=int(input('Enter the desired length( minimum 6): '))
        if length<6 :
            print('password length must be atleast 6')
            return
        print('select the character types  to include:')
        include_uppercase=input('include uppercase letters? (y/n): ').lower()=='y'
        include_lowercase=input('include lowercase letters? (y/n): ').lower()=='y'
        include_digits=input('include number? (y/n): ').lower()=='y'
        include_symbols=input('include special characters? (y/n): ').lower()=='y'

        if not(include_uppercase or include_lowercase or include_digits or include_symbols):
            print('you must select at least one character type')
            return
        character_pool=""
        if include_uppercase:
            character_pool +=string.ascii_uppercase
        if include_lowercase:
            character_pool +=string.ascii_lowercase
        if include_digits:
            character_pool +=string.digits
        if include_symbols:
            character_pool +=string.punctuation
        password = ''.join(random.choice(character_pool)for _ in range(length))
        print(f"generated password: {password}")
    except ValueError:
        print('valid input|please enter a valid number.')
while True:
    generate_password()
    repeate=input('\n do you want to generate another password? (y/n): ').lower()
    if repeate=='y':
        print('exciting password generator.stay secure!')
        break
        ***
        output:

        ---password generated--
Enter the desired length( minimum 6): 8
select the character types  to include
include uppercase letters? (y/n): S
include lowercase letters? (y/n): umi
include number? (y/n): 250
include special characters? (y/n): @
you must select at least one character type

 do you want to generate another password? (y/n): n

---password generated--
