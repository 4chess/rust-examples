NOTE!! As of this directory, 32 and forward, we will make more robust examples of fully working apps. 
Rust Encryption/Decryption otp


This application is a straightforward, command-line tool designed for basic file encryption and decryption using XOR methodology. It's built with Rust and offers a user-friendly interface for both generating encryption keys and processing files.

Features
The tool features three main functions:

Encrypting or decrypting files using a generated key.
Generating a secure encryption key.
A simple, interactive command-line interface.

How to Use ::
To use this tool, ensure you have Rust installed on your system. Compile the program by navigating to its directory and running cargo build --release. This generates an executable in the target/release directory.

Running the Program --
Execute the program from the command line in the target/release directory. Upon launch, you're presented with a menu offering three options:

Encrypt/Decrypt a file.
Generate an encryption key.
Exit the program.
Encrypting/Decrypting Files
To encrypt or decrypt a file, choose option 1, then enter the file name when prompted. The file should be in the same directory as the program or a relative path should be provided. The program will use the key from "key.key" for this process.

Generating an Encryption Key
Select option 2 to generate a new encryption key. You will be asked to specify the key length. The key is then saved as "key.key" in the program's directory and set to read-only for security.

Exiting the Program
Choose option 3 to exit the program.



//////////

