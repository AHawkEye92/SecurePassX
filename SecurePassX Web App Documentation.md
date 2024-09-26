## Overview

SecurePassX is a web application designed to enhance data security by providing tools for password strength evaluation, password generation, and ASCII encryption/decryption. The application is built using Flask, a lightweight web framework for Python.

## Features

- **Password Strength Checker**: Evaluates the strength of a given password based on various criteria.
- **Password Generator**: Generates random passwords of specified lengths.
- **ASCII Encryption/Decryption**: Encrypts and decrypts text using an ASCII cipher with a specified shift.

## Requirements

- Python 3.x
- Flask
- Random (Python's built-in module)

## Installation

To run the application, ensure you have Python installed, then install Flask using pip:

bash

Copy code

`pip install Flask`

## Running the Application

To run the application, execute the following command in your terminal:

bash

Copy code

`python app.py`

The application will be accessible at `http://127.0.0.1:5000/`.

## Application Structure

### Main Application Code

python

Copy code

`from flask import Flask, request, render_template_string import random`

- Imports necessary modules: Flask for web application functionality, `request` for handling form submissions, `render_template_string` for rendering HTML templates, and `random` for generating random characters.

### ASCII Cipher Functions

python

Copy code

`def asciicipher_encrypt(plaintext, shift):     # Encrypts a plaintext message using a shift value.`

- **Parameters**:
    - `plaintext`: The text to be encrypted.
    - `shift`: The number of positions to shift each character in the ASCII table.
- **Returns**: The encrypted message.

python

Copy code

`def asciidecrypt(encrypted_message, shift):     # Decrypts an encrypted message using a shift value.`

- **Parameters**:
    - `encrypted_message`: The text to be decrypted.
    - `shift`: The number of positions to shift each character back in the ASCII table.
- **Returns**: The decrypted message.

### Password Checker Function

python

Copy code

`def passwordchecker(password):     # Evaluates the strength of the provided password.`

- **Parameters**:
    
    - `password`: The password to be evaluated.
- **Returns**: A string indicating the strength of the password: "Very Weak", "Weak", "Strong", or "Very Strong".
    

### Random Character Generator

python

Copy code

`def Randomchar():     # Generates a random character from a set of categories.`

- **Returns**: A single random character (lowercase, uppercase, digit, or special character).

python

Copy code

`def Generate(passlen):     # Generates a random password of specified length.`

- **Parameters**:
    - `passlen`: The length of the password to be generated.
- **Returns**: A randomly generated password.

### Routes

#### Home Route

python

Copy code

`@app.route('/') def home():     # Renders the main page of the application with forms for various features.`

- **Returns**: An HTML page containing forms for checking password strength, generating passwords, and performing ASCII encryption and decryption.

#### Check Password Strength Route

python

Copy code

`@app.route('/check_password', methods=['POST']) def check_password():     # Receives a password and returns its strength.`

- **Methods**: POST
- **Returns**: A string indicating the strength of the submitted password.

#### ASCII Encryption Route

python

Copy code

`@app.route('/encrypt', methods=['POST']) def encrypt():     # Receives plaintext and a shift value, returns the encrypted message.`

- **Methods**: POST
- **Returns**: The encrypted message based on the input plaintext and shift.

#### ASCII Decryption Route

python

Copy code

`@app.route('/decrypt', methods=['POST']) def decrypt():     # Receives an encrypted message and a shift value, returns the decrypted message.`

- **Methods**: POST
- **Returns**: The decrypted message based on the input encrypted text and shift.

#### Generate Password Route

python

Copy code

`@app.route('/generate_password', methods=['POST']) def generate_password():     # Receives a length for the password and returns a generated password.`

- **Methods**: POST
- **Returns**: A randomly generated password of the specified length.