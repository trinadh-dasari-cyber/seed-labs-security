# 🧪 SEED Labs — Software & Linux Security Research

**Academic project — binary exploitation and Linux privilege escalation research as part of MS Cybersecurity coursework at University of Central Missouri**

> ⚠️ Disclaimer: All research was conducted in isolated SEED Lab virtual machine environments for academic purposes only.

---

## Overview

This project was completed as part of my MS Cybersecurity program at the University of Central Missouri. Through the SEED Labs curriculum I conducted hands-on exploitation research covering binary exploitation techniques, Linux privilege escalation vectors, and OS-level attack surfaces — building practical understanding that directly informs both offensive research and defensive hardening.

---

## Academic Context

- **Institution:** University of Central Missouri
- **Program:** MS Cybersecurity
- **Course:** Software Security
- **Lab Environment:** SEED Labs (Syracuse University curriculum)

---

## Labs Completed

### 1. Buffer Overflow Exploitation
- Exploited stack-based buffer overflows on 32-bit and 64-bit Linux systems
- Used GDB to analyze stack memory layouts, calculate offsets, and craft shellcode payloads
- Bypassed basic stack protections to achieve code execution

**Key concepts:** Stack layout, return address overwrite, shellcode injection, NOP sleds

### 2. Return-to-libc & ROP Chains
- Bypassed non-executable stack (NX bit) using return-to-libc technique
- Constructed ROP chains to achieve code execution without injecting shellcode
- Chained gadgets to call system("/bin/sh") via libc

**Key concepts:** NX bypass, ROP gadgets, libc base address calculation, ASLR interaction

### 3. Set-UID Privilege Escalation
- Investigated how misconfigured Set-UID programs can be abused for privilege escalation
- Exploited PATH hijacking by replacing trusted binaries with malicious versions
- Abused environment variable manipulation to influence privileged program behavior

**Key concepts:** Set-UID mechanics, PATH injection, environment variable attacks, least-privilege principle

### 4. Race Condition Vulnerabilities (TOCTOU)
- Demonstrated Time-of-Check to Time-of-Use race conditions in privileged programs
- Exploited the window between a file permission check and file access to write to protected locations

**Key concepts:** TOCTOU, race windows, symlink attacks, atomic operations

### 5. Dynamic Linker Abuse (LD_PRELOAD)
- Used LD_PRELOAD to inject custom shared libraries and intercept libc function calls
- Demonstrated how misconfigured environments allow library preloading in privileged contexts

**Key concepts:** Dynamic linking, shared library injection, LD_PRELOAD restrictions

---

## Tools Used

`GDB` `Python` `C` `Linux (Ubuntu)` `objdump` `readelf` `ltrace` `strace`

---

## What I Learned

- How memory is laid out on the stack and how overflows overwrite return addresses
- How modern defenses like NX and ASLR work and how attackers bypass them
- How Set-UID programs can be abused when least-privilege principles are not enforced
- How race conditions create exploitable windows in privileged code paths
- How these low-level attack techniques directly inform defensive hardening strategies

---

## Frameworks Referenced

- MITRE ATT&CK: T1055 (Process Injection), T1574 (Hijack Execution Flow), T1548 (Abuse Elevation Control Mechanism)
- CWE-121 (Stack-Based Buffer Overflow), CWE-367 (TOCTOU Race Condition)

---

## Skills Demonstrated

`Binary Exploitation` `Memory Analysis` `Privilege Escalation` `Linux Security` `Reverse Engineering` `Exploit Development` `Defensive Hardening`
