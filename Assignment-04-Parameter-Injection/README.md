Assignment 4: Command Parameter Injection



Category: Web Application Security  

Status: Completed  

Date: October 2025



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



CHALLENGE OVERVIEW



Exploited command parameter injection vulnerability in Safest Bank's online telephone directory application. Manipulated command-line parameters to execute arbitrary system commands and extract sensitive files from the web server.



Target: Safest Bank phone directory web application  

Goal: Extract sensitive system files and information



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



VULNERABILITIES EXPLOITED



\- Command injection through grep utility parameters

\- Insufficient input sanitization and filtering

\- Client-side validation bypass

\- Improper access control on system files

\- Weak command execution safeguards



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



TOOLS \& TECHNIQUES



\- Browser Developer Tools for HTML source analysis

\- Command injection payloads for arbitrary command execution

\- Unix/Linux command chaining techniques

\- File system traversal for locating sensitive data



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



ATTACK METHODOLOGY



Step 1: Analyzed HTML source to understand grep command usage

Step 2: Tested input fields for command injection points

Step 3: Bypassed client-side input filtering

Step 4: Crafted payloads using command separators and operators

Step 5: Executed arbitrary commands to enumerate system information

Step 6: Navigated filesystem to locate target files

Step 7: Extracted sensitive data including SSH keys and emails



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



KEY LEARNINGS



\- Command injection occurs when user input passed to system calls

\- Client-side validation provides no security protection

\- Shell metacharacters enable command chaining and execution

\- Web applications should never directly invoke system commands

\- Principle of least privilege critical for web server processes



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



DEFENSIVE MEASURES



\- Avoid system command calls in web applications entirely

\- Use language-specific functions instead of shell commands

\- Implement strict server-side input validation

\- Apply whitelist filtering for allowed characters

\- Run web applications with minimal privileges

\- Disable dangerous functions in production

\- Regular penetration testing and security audits



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



RESULTS



Questions Answered: 6/6  

Data Extracted: CPU info, emails, SSH keys, secret files  

Time: 5 hours



\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_



Back to Course Overview: README.md

