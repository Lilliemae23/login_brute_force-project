# login\_brute\_force-project

Simple PHP Login Security Lab – Brute Force \& Account Lockout



Project Overview

This project shows how login systems can be attacked using brute-force techniques and how account lockout can mitigate those attacks.

The environment was created on Kali Linux using PHP, and the exercise covers:

building a simple login page

attacking it with Hydra

observing the vulnerability

implementing account lockout protection

The project also reflects the real troubleshooting process beginners experience while learning web security concepts.



Learning Objectives

Understand how web login authentication works

Demonstrate a brute-force attack using Hydra

Observe how weak authentication can be exploited

Implement account lockout after failed attempts

Learn basic defensive coding in PHP

Tools \& Environment

Kali Linux

Apache Web Server

PHP

Hydra (brute-force tool)

RockYou wordlist



 
 Lab Setup

A simple PHP login page was created with hardcoded credentials:

Username: admin

Password: password123

The page accepts POST login requests and displays either success or failure.

Insert Screenshot = login page

brute-force-photos/login\_page.png

Login Page



 

 Brute Force Attack

Hydra was used to perform a dictionary-based brute-force attack against the login form using the RockYou password list.

The attack successfully discovered the valid credentials, demonstrating the weakness of having:

no rate limiting

no lockout

predictable password

Insert Screenshot — Hydra Attack Output

 

 Successful Login

Once the credentials were known, login succeeded through the browser.

Insert Screenshot — Successful Login



 Failed Login Attempts

The system was modified to track failed login attempts per user session.

Insert Screenshot — Failed Attempt Counter

 

 Account Lockout Mitigation

A lockout mechanism was implemented:

Failed attempts are counted

After 5 incorrect attempts, the account is locked

Further login attempts are blocked

This prevents brute-force attacks from continuing indefinitely.

Insert Screenshot — Account Lockout Message

 

 Security Insight

Brute-force attacks rely on unlimited login attempts.
Without controls, attackers can eventually guess passwords.

Account lockout reduces risk by:

limiting repeated attempts

slowing automated attacks

protecting weak credentials

This project demonstrates a foundational defensive control used in real authentication systems.

 

 Beginner Notes

This lab involved significant troubleshooting, including:

blank PHP pages

Apache configuration issues

POST vs GET handling

session tracking errors

Working through these issues was part of my learning process

 

 Key Takeaway

Even a very simple login system can be vulnerable.
Basic protections like account lockout dramatically improve security against automated attacks.

