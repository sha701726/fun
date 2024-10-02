## Overview

This document provides a detailed explanation of a Python script designed to encrypt and decrypt files using the `cryptography` library. The script is structured as a Jupyter Notebook and includes functionality for listing files, encrypting their contents, and decrypting them back to their original state. 

**Disclaimer:** This script is intended for educational purposes only. Misuse of encryption technologies for malicious purposes is illegal and unethical.

## Table of Contents

1. [Requirements](#requirements)
2. [Script Structure](#script-structure)
   - [Markdown Cells](#markdown-cells)
   - [Code Cells](#code-cells)
3. [Functions](#functions)
   - [encrypt()](#encrypt)
   - [decrypt()](#decrypt)
4. [Execution](#execution)
5. [Conclusion](#conclusion)

## Requirements

To run this script, you need:
- Python 3.6 or higher
- `cryptography` library

You can install the required library using:
```bash
pip install cryptography
```

## Script Structure

The script is divided into multiple cells that serve different purposes.

### Markdown Cells

Markdown cells are used for documentation and explanations. The script contains the following markdown sections:

- **Title:** Introduces the purpose of the script.
- **Append All The Files In A List Named As Files:** Describes the process of listing files to be encrypted.
- **Function To Encrypt The Files:** Provides a brief overview of the encryption function.
- **Function To Decrypt The Files:** Provides a brief overview of the decryption function.
- **Calling The Functions "encrypt() and decrypt()":** Explains how to execute the functions.

### Code Cells

Code cells contain the executable Python code. The main components are:

1. **Imports:**
   ```python
   import os
   from cryptography.fernet import Fernet
   ```

2. **File Listing:**
   ```python
   files = []
   for file in os.listdir():
       if file == "encryption.ipynb" or file == "key.dat":
           continue
       if os.path.isfile(file):
           files.append(file)

   print("PRINTNG THE FILES HERE: ", files)
   ```

3. **Encryption Function:**
   ```python
   def encrypt(files):
       ...
   ```

4. **Decryption Function:**
   ```python
   def decrypt(files):
       ...
   ```

5. **Main Execution Block:**
   ```python
   if __name__ == "__main__":
       decrypt(files)
   ```

## Functions

### encrypt()

This function encrypts all specified files using a generated key. 

**Parameters:**
- `files`: A list of file names to be encrypted.

**Key Steps:**
1. Generates a new encryption key.
2. Saves the key to a file named `key.dat`.
3. Reads each file's contents and encrypts them.
4. Writes the encrypted contents back to the original files.

### decrypt()

This function decrypts files using the previously saved key.

**Parameters:**
- `files`: A list of file names to be decrypted.

**Key Steps:**
1. Reads the encryption key from `key.dat`.
2. Reads each file's encrypted contents and decrypts them.
3. Writes the decrypted contents back to the original files.

## Execution

To execute the script, run the following command in your terminal or Jupyter Notebook environment:

```python
if __name__ == "__main__":
    # Call encrypt(files) to encrypt files
    decrypt(files)  # Uncomment to decrypt files
```

### Important Notes:
- By default, the script is set to decrypt files. Uncomment the `encrypt(files)` line to enable encryption.
- Ensure that the script is run in a directory where the target files are located.

## Conclusion

This Python script demonstrates basic file encryption and decryption using the `cryptography` library. It provides a simple interface for managing file security, making it useful for educational and legitimate security testing purposes. Always use such scripts responsibly and ethically.
