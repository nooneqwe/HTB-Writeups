# Sau — Hack The Box Writeup

## Overview

| Field      | Value   |
| ---------- | ------- |
| Difficulty | Easy    |
| OS         | Linux   |
| Status     | Retired |

## 1. Reconnaissance
### 1.1 Nmap Scan
Execution:
```bash
nmap -sC -sV --open -p- <TARGET-IP>
```
Result:
```bash
22/tcp    open  ssh     OpenSSH 8.2p1 Ubuntu 4ubuntu0.7 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 aa:88:67:d7:13:3d:08:3a:8a:ce:9d:c4:dd:f3:e1:ed (RSA)
|   256 ec:2e:b1:05:87:2a:0c:7d:b1:49:87:64:95:dc:8a:21 (ECDSA)
|_  256 b3:0c:47:fb:a2:f2:12:cc:ce:0b:58:82:0e:50:43:36 (ED25519)
55555/tcp open  http    Golang net/http server
| http-title: Request Baskets
|_Requested resource was /web
```
Analysis:
- SSH and HTTP (55555) service identified

Next:
- Perform web enumeration
## 2. Enumeration
### 2.1 Web Enumeration
Execution:
