# TryHackMe — Lo-Fi

**Difficulty:** Easy  
**Category:** Web  
**Platform:** TryHackMe

## 1. Description
Lo-Fi is a beginner-friendly web challenge focused on basic web enumeration and source code inspection.

## 2. Enumeration
I started by inspecting the HTML source code of the page and noticed that content was loaded dynamically using a GET parameter called `page`, for example:

`/?page=relax.php`

This indicated that the application might be including files based on user input.

---

## 3. Vulnerability
The application does not properly validate the value of the `page` parameter before including files.  
This allows an attacker to request arbitrary local files from the server.

This behavior represents a **Local File Inclusion (LFI)** vulnerability.

---

## 4. Exploitation
To confirm the vulnerability, I attempted to read a sensitive system file:

`/?page=../../../../etc/passwd`

The server returned the contents of the file, confirming that LFI was present.

After that, I accessed the flag file directly:

`/?page=../../../../flag.txt`

---

## 5. Flag
Flag obtained successfully.

---

## 6. What I learned
- How Local File Inclusion vulnerabilities occur
- How to identify insecure file inclusion via GET parameters
- Why user-controlled file paths are dangerous
- How attackers can read sensitive local files through LFI

- ## 7. What i want to learn
- More vulnerabilities about local files throuht LFI
