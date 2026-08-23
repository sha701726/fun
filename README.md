# 🔐 File Encryption & Decryption Tool (Python + Cryptography)

[![Python](https://img.shields.io/badge/Python-3.6%2B-blue.svg)](https://www.python.org/)
[![Library](https://img.shields.io/badge/Library-cryptography-green.svg)](https://pypi.org/project/cryptography/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Jupyter Notebook](https://img.shields.io/badge/Made%20with-Jupyter-orange.svg)](https://jupyter.org/)

A lightweight **Python script for file encryption and decryption** using the `cryptography` library's Fernet symmetric encryption. Built as a Jupyter Notebook, this tool automatically detects files in a directory, encrypts their contents with a securely generated key, and decrypts them back to their original state.

Great for learning **symmetric encryption**, **file security automation**, and **Python cryptography basics**.

> ⚠️ **Disclaimer:** This project is intended strictly for **educational purposes** and legitimate security testing. Misuse of encryption tools for unauthorized or malicious purposes is illegal and unethical. Use responsibly.

---

## ✨ Features

- 🔑 Generates a secure Fernet encryption key automatically
- 📂 Auto-detects and lists all files in the working directory
- 🔒 Encrypts file contents in place
- 🔓 Decrypts files back to their original content using the saved key
- 📓 Simple, readable Jupyter Notebook implementation — beginner friendly

---

## 📑 Table of Contents

1. [Requirements](#requirements)
2. [Installation](#installation)
3. [Script Structure](#script-structure)
4. [Functions](#functions)
   - [encrypt()](#encrypt)
   - [decrypt()](#decrypt)
5. [Usage](#usage)
6. [Notes](#important-notes)
7. [Disclaimer](#disclaimer)
8. [License](#license)

---

## Requirements

- Python 3.6 or higher
- `cryptography` library

## Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/sha701726/fun.git
cd fun
pip install cryptography
```

---

## Script Structure

The notebook is organized into clearly documented Markdown and Code cells for easy readability.

### Markdown Cells
- **Title** — introduces the purpose of the script
- **File Listing** — explains how files are collected for processing
- **Encrypt Function** — overview of the encryption logic
- **Decrypt Function** — overview of the decryption logic
- **Function Calls** — how to run encryption/decryption

### Code Cells

**Imports**
```python
import os
from cryptography.fernet import Fernet
```

**File Listing**
```python
files = []
for file in os.listdir():
    if file == "encryption.ipynb" or file == "key.dat":
        continue
    if os.path.isfile(file):
        files.append(file)
print("PRINTING THE FILES HERE: ", files)
```

**Main Execution Block**
```python
if __name__ == "__main__":
    decrypt(files)
```

---

## Functions

### `encrypt()`
Encrypts all specified files using a newly generated key.

**Parameters:** `files` — list of file names to encrypt

**Steps:**
1. Generates a new Fernet encryption key
2. Saves the key to `key.dat`
3. Reads and encrypts each file's contents
4. Writes encrypted content back to the original files

### `decrypt()`
Decrypts files using the previously saved key.

**Parameters:** `files` — list of file names to decrypt

**Steps:**
1. Reads the encryption key from `key.dat`
2. Reads and decrypts each file's contents
3. Writes decrypted content back to the original files

---

## Usage

Run the notebook or script:

```python
if __name__ == "__main__":
    # encrypt(files)   # Uncomment to encrypt files
    decrypt(files)      # Default: decrypts files
```

### Important Notes
- By default, the script runs in **decrypt mode**. Uncomment `encrypt(files)` to enable encryption.
- Always run the script from the directory containing the target files.
- Keep `key.dat` safe — losing it means the encrypted files cannot be recovered.

---

## Disclaimer

This project is built purely for **educational and learning purposes** — to understand symmetric encryption concepts using Python's `cryptography` library. Do not use it for unauthorized access to or tampering with data you don't own or have explicit permission to work with.


**Keywords:** python file encryption, python decrypt files, cryptography fernet python, symmetric encryption script, jupyter notebook encryption tool, python security automation
