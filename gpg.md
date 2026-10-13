To encrypt test.pdf using GPG on Linux:
1. Password-based encryption (symmetric)
gpg --symmetric --cipher-algo AES256 test.pdf

- Creates test.pdf.gpg
- Prompts you to enter a password
- Original test.pdf remains unchanged
Decrypt:
gpg --output test.pdf --decrypt test.pdf.gpg



