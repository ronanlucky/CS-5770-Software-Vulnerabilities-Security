\# Assignment 3: SQL Injection \& Authentication Bypass



Category: Web Application Security  

Status: ✅ Completed  

Date: October 2025



---



\## Challenge Overview



Exploited SQL injection vulnerability in banking web application to bypass authentication and extract sensitive customer data including credit card information and account details.



Target: "Safest Bank" online banking application  

Goal: Bypass authentication and retrieve database records



---



\## Vulnerabilities Exploited



\- SQL Injection in login form authentication

\- Insufficient input validation and sanitization

\- Direct SQL query construction from user input

\- Database error message disclosure

\- Improper access control on sensitive data



---



\## Tools \& Techniques



\- Browser Developer Tools - HTML source analysis and request manipulation

\- SQL Injection payloads - Authentication bypass and data extraction

\- Manual testing - Iterative query refinement based on error messages

\- UNION-based injection - Database schema enumeration



---



\## Attack Methodology



1\. Analyzed HTML source code for form submission parameters

2\. Tested input fields for SQL injection vulnerabilities

3\. Triggered SQL error messages to gather database information

4\. Crafted injection payloads to bypass authentication logic

5\. Used UNION queries to extract data from database tables

6\. Enumerated database structure (table names, column names)

7\. Retrieved sensitive customer information systematically



!\[SQL Injection Attack](screenshots/sql-injection-demo.png)



---



\## Key Learnings



\- SQL injection occurs when user input is directly embedded in SQL queries

\- Error messages can reveal critical database structure information

\- Authentication logic vulnerable when relying solely on SQL queries

\- UNION-based injection enables extraction of arbitrary data

\- Input validation must occur on server-side, not just client-side



---



\## Defensive Measures



\- Use parameterized queries (prepared statements)

\- Implement input validation and sanitization

\- Apply principle of least privilege for database accounts

\- Disable detailed error messages in production

\- Use ORM frameworks to abstract SQL operations

\- Implement Web Application Firewall (WAF)

\- Regular security testing and code reviews



---



\## Results



Questions Answered: 5/5  

Data Extracted: Customer names, credit card numbers, account balances  

Time: ~4 hours



---



\[Back to Course Overview](../README.md)

