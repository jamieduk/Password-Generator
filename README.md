::: {align="center"}
# 🔐 Password Lab

### A browser-based workbench for passwords, hashes, and exposure checks.

**Generate. Inspect. Check.**\
A lightweight, privacy-conscious toolkit that runs in your browser ---
no account or backend required.

![HTML5](https://img.shields.io/badge/HTML5-single%20file-E34F26?logo=html5&logoColor=white)
![Vanilla
JavaScript](https://img.shields.io/badge/JavaScript-vanilla-F7DF1E?logo=javascript&logoColor=black)
![Backend](https://img.shields.io/badge/Backend-none-22C55E)
![License](https://img.shields.io/badge/License-not%20specified-lightgrey)
:::

------------------------------------------------------------------------

## ✨ What is Password Lab?

Password Lab is a self-contained web app for generating passwords,
calculating common cryptographic hashes, and optionally checking a
password against the **Have I Been Pwned (Pwned Passwords)** dataset.

It combines a clean, responsive interface with practical tools --- all
in a single HTML file, with no framework or build step.

## 🚀 Features

### 🎲 Password generator

-   Cryptographically strong random selection using the browser's Web
    Crypto API.
-   Adjustable length from **6 to 250 characters**.
-   **8 characters by default**, with the option to choose a shorter or
    longer password.
-   Toggle lowercase, uppercase, numbers, and special characters.
-   Copy a generated password with one click.
-   Live, approximate password-strength estimate.

### 🧪 Hash inspector

-   Calculate **SHA-1, SHA-256, SHA-384, and SHA-512** digests.
-   Copy individual hash results.
-   Send the generated password to the hash inspector without retyping.
-   MD5 is listed for reference, but this app's browser Web Crypto
    implementation does not support calculating it.

### 🛡️ Password exposure check

-   Optional lookup against the Pwned Passwords corpus.
-   Uses the service's **k-anonymity range method**.
-   Sends only the first **5 hexadecimal characters** of the locally
    calculated SHA-1 hash to the range endpoint --- not the plaintext
    password or full hash.
-   Warns when the matching hash suffix appears in the dataset.

### 🎨 Simple by design

-   One self-contained HTML file.
-   No frameworks, package installation, or build process.
-   Responsive layout for smaller screens.
-   Accessible labels and visible keyboard-focus styling.
-   Core password generation works locally in a compatible browser.

## 🖥️ Get started

### Option 1 --- Run locally

1.  Download or clone the repository.
2.  Open `index.html` in a modern browser.
3.  Use **Generator** to create a password, or open **Advanced tools**
    to calculate hashes and check exposure.

> **Tip:** Browser APIs such as clipboard access and Web Crypto may be
> restricted when a page is opened directly from a file. If a feature is
> unavailable, try serving the page from `localhost` or publishing it
> with GitHub Pages.

### Option 2 --- Publish with GitHub Pages

1.  Add the app's HTML file to your GitHub repository.
2.  Name the file `index.html` so GitHub Pages can use it as the site
    entry point.
3.  Open **Settings → Pages** in the repository.
4.  Select the branch and folder containing `index.html`, then save.
5.  Visit the published URL and test the tools.

No build command or dependency installation is required.

## 🔒 Privacy & security

Password Lab is designed to process passwords in your browser.

-   **Password generation is local.** Random character selection uses
    `crypto.getRandomValues()`.
-   **Hash calculation is local.** Supported digests are calculated with
    the browser's Web Crypto API.
-   **The exposure check uses the internet.** The app calculates a SHA-1
    hash locally and sends only its first five hexadecimal characters to
    the Pwned Passwords range endpoint. It does not send the plaintext
    password or full hash as part of that range request.
-   **A clean result is not a guarantee.** No match in the checked
    dataset does not prove a password has never leaked or that an
    account is safe.
-   **A match is a warning.** Do not use a password found in the
    dataset. If it protects an existing account, change it and update
    any other accounts where it was reused.

### Important limitations

Password Lab is a handy utility, **not a complete security audit**.

-   The strength meter is only a rough estimate based on length,
    selected character pool, and a few simple pattern checks. It cannot
    guarantee safety.
-   Hashes are fingerprints, **not encryption**. This app does not
    decrypt hashes.
-   MD5 and SHA-1 are included/listed for compatibility or
    identification only; neither should be used to store passwords
    securely. Systems storing passwords should use a dedicated
    password-hashing algorithm such as Argon2id, scrypt, or bcrypt.
-   The exposure check requires an internet connection and may be
    blocked by browser settings, extensions, network policy, or service
    availability.
-   Avoid entering real passwords on pages or devices you do not trust.
    For important accounts, use a reputable password manager and unique
    passwords.

## 🧰 Built with

-   **HTML** --- structure
-   **CSS** --- responsive layout and styling
-   **Vanilla JavaScript** --- application logic and password generation
-   **Web Crypto API** --- secure random values and supported digest
    algorithms
-   **Pwned Passwords range API** --- optional password-exposure lookup

No external JavaScript libraries are required.

## 📁 Project structure

``` text
.
└── index.html    # Complete app: markup, styles, and JavaScript
```

If the app has a different filename in your repository, rename it to
`index.html` or configure your GitHub Pages entry point accordingly.

## 🤝 Contributing

Suggestions, bug reports, accessibility improvements, and pull requests
are welcome.

1.  Fork the repository.
2.  Create a branch for your change.
3.  Make the change and test it in a modern browser.
4.  Open a pull request explaining what changed and how you tested it.

Please keep privacy and security claims accurate; no password should be
described as "unhackable."

## 📜 License

No license has been specified here. Add a `LICENSE` file before
publishing if you want to make the project's reuse and distribution
terms explicit.

------------------------------------------------------------------------

::: {align="center"}
**Password Lab** · Small, focused tools for better password hygiene.

`<sub>`{=html}Stay unique. Stay cautious. Use a password
manager.`</sub>`{=html}
:::
