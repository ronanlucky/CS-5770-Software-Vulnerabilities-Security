# Assignment 3: SQL Injection & Authentication Bypass

Category: Web Application Security  
Status: Completed  
Date: October 2025

________________________________________________________________________________

CHALLENGE OVERVIEW

Exploited SQL injection vulnerability in banking web application to bypass authentication and extract sensitive customer data including credit card information and account details.

Target: Safest Bank online banking application  
Goal: Bypass authentication and retrieve database records

________________________________________________________________________________

VULNERABILITIES EXPLOITED

• SQL Injection in login form authentication
• Insufficient input validation and sanitization
• Direct SQL query construction from user input
• Database error message disclosure
• Improper access control on sensitive data

________________________________________________________________________________

TOOLS & TECHNIQUES

• Browser Developer Tools for HTML source analysis
• SQL Injection payloads for authentication bypass
• Manual testing with iterative query refinement
• UNION-based injection for database enumeration

________________________________________________________________________________

ATTACK METHODOLOGY

Step 1: Analyzed HTML source code for form parameters
Step 2: Tested input fields for SQL injection vulnerabilities
Step 3: Triggered SQL error messages to gather database info
Step 4: Crafted injection payloads to bypass authentication
Step 5: Used UNION queries to extract database data
Step 6: Enumerated database structure
Step 7: Retrieved sensitive customer information

________________________________________________________________________________

KEY LEARNINGS

• SQL injection occurs when user input directly embedded in queries
• Error messages reveal critical database structure information
• Authentication vulnerable when relying solely on SQL queries
• UNION-based injection enables extraction of arbitrary data
• Input validation must occur server-side

________________________________________________________________________________

DEFENSIVE MEASURES

• Use parameterized queries (prepared statements)
• Implement input validation and sanitization
• Apply principle of least privilege for database accounts
• Disable detailed error messages in production
• Use ORM frameworks to abstract SQL operations
• Implement Web Application Firewall (WAF)
• Regular security testing and code reviews

________________________________________________________________________________

RESULTS

Questions Answered: 5/5  
Data Extracted: Customer names, credit card numbers, balances  
Time: 4 hours

________________________________________________________________________________

Back to Course Overview: ../README.md