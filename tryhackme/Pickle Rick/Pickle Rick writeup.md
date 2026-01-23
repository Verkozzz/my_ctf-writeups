# 🥒 Pickle Rick — TryHackMe

**Difficulty:** Easy  
**Category:** Web / Privilege Escalation  
**Platform:** TryHackMe  

---

## 🧪 Objective

Exploit a vulnerable web server and collect **three ingredients** to help Rick transform back into a human.

---

## 🔍 Enumeration

### Web Enumeration

Accessing the website and checking common paths revealed:
/robots.txt


Contents of `robots.txt`:
Wubbalubbadubdub

This looked like a password or authentication clue.

---

## 🔑 Authentication

Found username:
R1ckRul3s


Using the credentials, access to the **web command panel** was obtained.

---

## 🥇 First Ingredient

Using the web command interface:
ls

Revealed a file containing the first ingredient.

✅ First ingredient obtained



🥈 Second Ingredient

The cat command was disabled:
Command disabled to make it hard for future PICKLEEEE RICCCKKKK
Bypassing restrictions using less:

less /home/rick/second ingredients


✅ Second ingredient obtained

🧑‍💻 Privilege Escalation

Checking sudo permissions:

sudo -l


Output:

(ALL) NOPASSWD: ALL


This means the user www-data can execute any command as root without a password.

🥉 Third Ingredient (Root)

Accessing root directory:

sudo ls /root
sudo less /root/3rd.txt


!!!ROOM IS DONE
