# AES File Decryption Tool

This Python script provides a simple GUI-based decryption tool using the AES encryption algorithm. It allows users to select an encrypted file and decrypt it using a provided key.
r

## Features
- Uses AES encryption in **CBC mode** for secure decryption.
- Handles both **text and binary files** automatically.
- Provides a **GUI file selection** using `tkinter`.
- Ensures **proper padding removal** for accurate decryption.

## Requirements
Ensure you have Python installed along with the required dependencies:

```sh
pip install pycryptodome
```

## How It Works
1. The script opens a **file dialog** to select an encrypted file.
2. It **prompts the user** for a decryption key.
3. The selected file is decrypted using **AES CBC mode**.
4. The output is saved as **`decrypted.txt`** if it is a text file or as a **binary file** otherwise.

## Usage
Run the script using Python:

```sh
python decrypt.py
```

### Expected Input
- An **encrypted file** (previously encrypted using AES-CBC with the same key).
- A **16-byte (or more) decryption key**.

### Output
- A decrypted file named **`decrypted.txt`** (if the content is text).
- A decrypted **binary file** (if the content is not text).

## Code Breakdown
- **File Selection**: Uses `tkinter.filedialog` to let the user choose the encrypted file.
- **AES Decryption**:
  - Reads the **IV (Initialization Vector)** from the file.
  - Decrypts the content using **AES with CBC mode**.
  - Removes **padding** to restore the original data.
- **File Handling**:
  - If the decrypted data is **text**, it saves it as `decrypted.txt`.
  - If the decrypted data is **binary**, it saves it as a raw binary file.

## Example
```
Please provide your decryption key (16-byte min): mysecretpassword
Decryption complete! File saved as decrypted.txt (UTF-8 text).
```

## Notes
- Ensure the key used for decryption is **the same** as the encryption key.
- The script expects the encrypted file to have a **16-byte IV** at the beginning.
- If decryption fails, check that you are using the **correct key** and that the file was encrypted properly.

## License
This project is licensed under the **MIT License**.

---

Enjoy decrypting your files securely! 🔐

