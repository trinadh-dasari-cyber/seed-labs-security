# 🧪 SEED Labs — Software & Linux Security Research

**Hands-on exploitation research covering binary exploitation, privilege escalation, and OS-level attack surfaces**

> ⚠️ Disclaimer: All research was conducted in isolated SEED Lab virtual machine environments for academic purposes only.

---

## Overview

This project covers a series of structured security research labs from the SEED Labs curriculum — focusing on low-level exploitation techniques, Linux privilege escalation vectors, and OS-level attack surfaces. Each lab builds practical understanding that directly informs both offensive research and defensive hardening.

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

## Skills Demonstrated

`Binary Exploitation` `Memory Analysis` `Privilege Escalation` `Linux Security` `Reverse Engineering` `Exploit Development` `Defensive Hardening`

---

## Frameworks Referenced

- MITRE ATT&CK: T1055 (Process Injection), T1574 (Hijack Execution Flow), T1548 (Abuse Elevation Control Mechanism)
- CWE-121 (Stack-Based Buffer Overflow), CWE-367 (TOCTOU Race Condition)
