# Facts — Hack The Box Writeup

## Overview

| Field      | Value   |
| ---------- | ------- |
| Difficulty | Easy    |
| OS         | Linux   |
| Status     | Active  |

Facter is an easy machine featuring a vulnerable CMS (content Management System). The identified vulnerability allows initial access to the target system. Improper privileges assigned to a user enable privilege escalation, leading to retrive of the root flag using an installed tool.

## 1. Reconnaissance
### 1.1 Nmap scan
Execution:
```bash
nmap -sC -sV --open -p- <TARGET-IP>
```
Result:
```bash
22/tcp    open  ssh     OpenSSH 9.9p1 Ubuntu 3ubuntu3.2 (Ubuntu Linux; protocol 2.0)
80/tcp    open  http    nginx 1.26.3 (Ubuntu)
|_http-server-header: nginx/1.26.3 (Ubuntu)
|_http-title: Did not follow redirect to http://facts.htb/
54321/tcp open  http    Golang net/http server
|_http-title: Did not follow redirect to http://<Target-IP>:9001
```
Analysis:
- SSH and two HTTP services identified (80, 54321)
- Redirection to facts.htb
- Possible Golang-based HTTP service on port 54321 and nginx 1.26.3 on port 80

Next:
- Add facts.htb to /etc/hosts
- Perform web enumeration
---

## Note

This writeup is intentionally partial as the machine is currently active.  
To respect Hack The Box rules, exploitation details and privilege escalation steps will be added once the machine is retired.
