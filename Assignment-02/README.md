\# Assignment 2: Unix Security \& Privilege Escalation



\*\*Category:\*\* Systems Security | Privilege Escalation  

\*\*Status:\*\* ✅ Completed  

\*\*Date:\*\* October 2025



---



\## 🎯 Challenge Overview



Exploited vulnerabilities in four set-GUID Unix programs to achieve privilege escalation. Identified insecure use of `system()` function and environment variables to gain elevated group privileges.



\*\*Target:\*\* Four programs (`prog1-4`) with SGID bits set, owned by groups `bsp1-4`  

\*\*Goal:\*\* Execute `/bin/grade` with elevated group privileges



---



\## 🔍 Vulnerabilities Exploited



\- \*\*Unsafe system() Calls:\*\* Shell command injection via environment manipulation

\- \*\*PATH Variable Exploitation:\*\* Redirected program execution to malicious binaries

\- \*\*Symbolic Link Attacks:\*\* File system manipulation for unauthorized access

\- \*\*Environment Injection:\*\* Modified LD\_PRELOAD, LD\_LIBRARY\_PATH for privilege escalation

\- \*\*Set-GUID Abuse:\*\* Leveraged elevated permissions for unauthorized operations



---



\## 🛠️ Tools \& Techniques



\*\*Analysis:\*\*

\- grep (searched for insecure functions: `system()`, `dlopen()`, `strcpy()`)

\- ls -la (examined file permissions and SGID bits)

\- strace (traced system calls)



\*\*Exploitation:\*\*

\- Environment variable manipulation (PATH, LD\_PRELOAD)

\- Symbolic link creation (`ln -s`)

\- Shell injection techniques

\- Dynamic library hijacking



---



\## 📊 Exploitation Process



\### Understanding Set-GUID

Programs with SGID bit (`-rwxr-sr-x`) execute with the effective group ID of the file owner, granting temporary elevated privileges.



\### Attack Methodology

1\. \*\*Source Code Analysis:\*\* Identified unsafe `system()` calls in provided C programs

2\. \*\*Environment Manipulation:\*\* Modified PATH to point to attacker-controlled directories

3\. \*\*Malicious Binary Creation:\*\* Created replacement utilities that execute with elevated privileges

4\. \*\*Symbolic Link Exploitation:\*\* Redirected file access to bypass restrictions

5\. \*\*Privilege Validation:\*\* Called `/bin/grade` to verify successful exploitation



\### Key Insight

Understanding how `system()` resolves external commands through environment variables is critical. Programs that trust user-controlled environments when making privileged operations are vulnerable to exploitation.



---



\## 💡 Key Learnings



\*\*Technical Skills:\*\*

\- Understanding Unix permission model and set-UID/set-GID mechanics

\- Environment variable security implications

\- Recognizing insecure coding patterns in C (unsafe library functions)

\- Privilege escalation techniques in Unix systems



\*\*Security Insights:\*\*

\- `system()` function is inherently dangerous due to shell interpretation

\- Environment variables control program behavior and can be weaponized

\- Set-UID/Set-GID programs require extreme care in implementation

\- Input sanitization is critical even for seemingly safe operations



---



\## 🛡️ Defensive Countermeasures



\*\*Secure Coding Practices:\*\*

\- Avoid `system()` - use `execve()` with explicit arguments instead

\- Sanitize and validate all inputs rigorously

\- Reset environment variables in privileged programs

\- Use absolute paths for all external program calls

\- Drop privileges immediately after critical operations



\*\*System Hardening:\*\*

\- Minimize set-UID/set-GID programs on systems

\- Regular security audits of privileged binaries

\- Implement least privilege principle

\- Use mandatory access controls (SELinux, AppArmor)

\- Monitor for suspicious privilege escalation attempts



---



\## 📈 Results



\- \*\*Programs Exploited:\*\* 4/4 (100%)

\- \*\*Groups Compromised:\*\* bsp1, bsp2, bsp3, bsp4

\- \*\*Exploitation Techniques:\*\* Environment manipulation, symbolic links, PATH hijacking

\- \*\*Time Investment:\*\* ~5 hours



---



\## 🎓 Professional Impact



Skills developed for:

\- Penetration Testing: Privilege escalation techniques

\- Security Auditing: Identifying unsafe coding patterns

\- Incident Response: Understanding attacker escalation methods

\- Secure Development: Writing secure privileged programs



---



\*\*Back to Course Overview:\*\* ../README.md

