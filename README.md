# Brute Forcing an FTP Server

In this lab, you will practice exploration techniques, brute force attacks, and privilege escalation in a controlled environment. Your mission is to access an FTP server, discover weak credentials, and obtain two hidden flags. In this lab, you will learn:


- Analysis of misconfigured services (Anonymous FTP)
- Use of real password dictionaries
- Execution of brute force attacks
- Privilege escalation in Linux operating systems



## 📄 Instructions

- The server has anonymous FTP access enabled.
- Evidence of poor password practices has been found.
- Some system users might be using weak passwords.
- It is your responsibility to investigate and exploit the vulnerable configurations.


1. **Connect as an anonymous user**

    - Use an FTP client to connect with the user `anonymous`.
    - Explore the available files.
    - Pay attention to possible clues.

2. **Perform a brute force attack**

    - Use a tool like `hydra` along with a password dictionary.
    - Your goal is to gain access as certain system users.

3. **Obtain the first flag**

    - Once inside the system as a valid user, check their home directory.
    - Look for the flag.

4. **Escalate privileges**

    - Discover how to gain administrator (root) permissions using another system user.
    - Retrieve the second flag from a protected location.


## Flag #1

- 📁 Location: in one of the user's directories  
- 🔑 Requires: finding their credentials through brute force


## Flag #2

- 📁 Location: in a restricted system area  
- 🔑 Requires: escalating privileges to gain administrator access

## Recommended Tools

- FTP client (`ftp`)
- `hydra`
- Password dictionary like `rockyou.txt` (available in many security distributions)

**Remember:** there are no magic solutions. Observe, reason, and use the appropriate tools. Knowledge is your best ally.

Happy Hacking!