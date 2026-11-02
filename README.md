# Crypto Messenger

A small, browser-based message encryption experiment with a neon, sci-fi look. Type a message, encrypt it into a shareable text block, then decrypt it later with the same passphrase.

> **Please read the safety note:** This is an experimental learning project, not a security-reviewed messaging product. Do not use it to protect passwords, financial details, private records, or anything that would cause harm if exposed.

## The story behind it

Imagine a message courier in a neon city. Before carrying a note across town, the courier places it in a locked envelope that only someone with the right passphrase can open.

Crypto Messenger turns that idea into a tiny interactive demo. The glowing interface, “alien text” animation, and control-panel styling are there for atmosphere. The real project is one HTML file that lets you experiment with encryption and decryption in a web browser.

## What it does

- Encrypts and decrypts text in your browser.
- Uses the CryptoJS library loaded from a public CDN.
- Provides controls for passphrase-based key setup, salt, initialization vector (IV), HMAC verification, key size, and cipher mode.
- Shows a password-strength estimate and a few visual statistics.

The output is a text block containing the encrypted message and the information the page needs for decryption. Share that block separately from the passphrase.

## Run it on your computer

You do not need to install an app, Node.js, or Python.

1. Open [crypto_messenger_enhanced.html](crypto_messenger_enhanced.html) in this repository.
2. Choose **Download raw file** (or download the repository as a ZIP and open the HTML file inside it).
3. Open the downloaded HTML file in a current browser such as Chrome, Edge, or Firefox.
4. Enter a message and a passphrase, then choose **ENCRYPT**.
5. Copy the resulting text block. To decrypt it later, paste the block into the message box and enter the same passphrase.

The page loads CryptoJS from Cloudflare's CDN, so an internet connection is needed when opening the file. It also loads Google Fonts for its appearance; the fonts are decorative.

## Run it as a website

The repository stores the page's source code. To make GitHub host it as a website:

1. Open this repository's **Settings**.
2. Select **Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**.
4. Choose the `main` branch and the `/(root)` folder, then save.
5. After GitHub finishes publishing, open the website address it shows and add `/crypto_messenger_enhanced.html` to the end.

GitHub Pages settings are not enabled by this README; you need to turn them on in the repository settings.

## Important limits

- **Not independently reviewed:** This project is for learning and experimentation. It has not been audited by a security professional.
- **The algorithm menu is misleading in this version:** the encryption and decryption code calls AES directly, even though the screen offers other algorithm names. Leave **AES** selected.
- **Choose the same mode when encrypting and decrypting:** the selected mode is not saved in the output block. **CBC** is selected by default.
- **The generated-key button is not suitable for real secrets:** its current code uses `Math.random()`. Use a strong passphrase from a trusted password manager if you are only experimenting.
- **Some numbers are just demonstrations:** the password-strength and crack-time displays are rough estimates, and the compression percentage is randomly generated.
- **Keep the passphrase private:** anyone with both the encrypted block and its passphrase may be able to read the message.
- **The page has no app server:** the current HTML contains no code that sends or saves message contents to a server. Your browser still loads the CryptoJS script and fonts from the internet, and browser extensions or malware can affect what happens on your computer.

For experiments, keep the built-in options enabled (salt, PBKDF2, IV, and HMAC), use **AES**, and avoid **ECB**. These suggestions do not make the project suitable for sensitive information.

## Project files

- `crypto_messenger_enhanced.html` — the complete browser page.

There is currently no license file. Publicly viewing the code does not by itself grant permission to reuse or redistribute it.
