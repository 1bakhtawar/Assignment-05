🔹 Requirements
1. Data Storage (In-Memory Dictionary)
Each entry is stored as:
stored_data = {
    "user1_data": {"encrypted_text": "some_ciphertext", "passkey": "hashed_passkey"},
    ...
}
Passkeys must be hashed (e.g., SHA-256).
2. Secure Encryption & Decryption
Encrypt data using Caesar cipher or Fernet (from cryptography library).
Decrypt only when the correct passkey is provided.
3. Authentication & Security
Allow three attempts before forcing a reauthorization/login page.
Display failed attempts count.
4. Streamlit UI (User-Friendly Interface)
Home Page: Options to store new data or retrieve data.
Insert Data Page:
User enters text + passkey, and it’s stored securely.
Retrieve Data Page:
User provides a passkey to decrypt data.
If failed 3 times, redirect to the Login Page for reauthorization.
Login Page: Simple login mechanism before retrying.


🔹 Additional Challenges
Data Persistence

Store encrypted data in a JSON file instead of memory.
Load data on app startup.
Advanced Security Features

Time-based lockout for failed attempts.
Use PBKDF2 hashing instead of SHA-256 for extra security.
Multi-User System

Allow multiple users to store and retrieve their own data.
Use a user authentication system with Streamlit.
