# Cipher — Key Forge / Encoder / Decoder

A browser-based, client-side homophonic substitution cipher toolkit. Three self-contained HTML tools, no server, no dependencies, no data leaves your machine:

- **`keygen.html`** — generates a cipher key file
- **`encoder.html`** — encrypts text using a key file
- **`decoder.html`** — decrypts ciphertext using the same key file

## What it does

Every printable character (letters, digits, punctuation, space, newline) is mapped to a large set of interchangeable disguises. Instead of one character always becoming the same output symbol, the encoder picks a different disguise essentially every time, so identical letters in your message don't look identical in the ciphertext. The key file is what defines those mappings, and it's generated using a cryptographically secure random source, not a simple shuffle.

The encoder and decoder must be loaded with the **exact same key file** to work together. Different key, no readable output. There's no password recovery, no backdoor, and no way to decrypt a message without the matching key file, by design.

## How to use it

1. Open `keygen.html` in a browser and forge a key file. Save it somewhere safe.
2. Share that key file with whoever you want to communicate with, through a channel you trust.
3. Use `encoder.html` + the key file to turn plaintext into ciphertext.
4. The recipient uses `decoder.html` + the same key file to read it.

No installation, no accounts, no internet connection required after the page loads.

## What this is (and isn't)

This is a proof-of-concept cipher project, built to explore classic substitution-cipher weaknesses and one way to address them. It's meant for casual, low-stakes privacy between people who already trust each other, think "keeping nosy people out of a group chat," not "protecting anything that actually matters."

---

## WARNING ⚠️

**This is not AES. This is not a real security tool. Do not use this for passwords, financial information, medical information, legal matters, or anything where being wrong has real consequences.**

This is a large substitution cipher. It is not resistant to a sufficiently motivated or resourced attacker, and it has known theoretical weaknesses common to this entire class of cipher. If someone with real cryptanalysis skill, time, and enough intercepted ciphertext decides to go after it, it can be broken. There is no authentication, so tampered ciphertext will not be detected, it'll just decode into garbage silently.

Use this for fun, for learning, for casual privacy among friends. Do not use it to protect anything you'd actually be upset to lose.
