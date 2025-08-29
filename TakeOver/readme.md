# TryHackMe Takeover Writeup: GoBuster for vHost Enumeration

Room Link: [Takeover](https://tryhackme.com/room/takeover)

---

## GoBuster (Always a Go-To Tool) vhost

i went for gobuster since i don’t know about nmap and other tool.  
as the title suggest subdomain enemuration, i went for looking for any open subdomain , since this is virtually hosted domain instead of dns i went for vhost  

so for that first you have to update your gobuster to version 3.6 or above as it is not available in below version.  

---

### step 1  
we will be adding out domain ip and name in etc/hosts  

---

### step 2  
after that we will be going for gobuster 

```bash
gobuster vhost -u YOUR_TARGET_DOMAIN \
  -w YOUR_WORD_LIST \
  --append-domain \
  --exclude-length YOUR_LENGTH \
  -k
```

| Parameter          | Description                                                                             | Example                                                                |
| ------------------ | --------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| `vhost`            | Mode for virtual host enumeration. Tells Gobuster to brute force vHosts.                | `gobuster vhost ...`                                                   |
| `-u`               | Target domain URL (must be in `/etc/hosts` mapped to IP).                               | `-u https://target.thm`                                                 |
| `-w`               | Path to the wordlist containing possible subdomain/vhost names.                         | `-w wordlist.txt` |
| `--append-domain`  | Appends the base domain to each word in the wordlist (e.g. `admin → admin.target.com`). | `--append-domain`                                                      |
| `--exclude-length` | Exclude responses with a specific content length (filters out false positives).         | `--exclude-length 3021`                                                |
| `-k`               | Ignore SSL/TLS certificate errors (useful if site uses self-signed certs).              | `-k`                                                                   |



to get wordlist check with list of subdomain which you can find in Tools/wordlists/SecLists/Discovery/DNS  folder , just explore a bit.  

---

### step 3  
now you will get the subdomain, just add those subdomain in your etc/hosts do remember there ip will be same as domain ip  

---

### step 4  
go to website and try entering all the extracted subdomain one by one  

---

### step 5  
you can check for certificate and can find open dns  

---

### final  
Hurray you got your answer  

i will really suggest you to read gobuster vhost -h , this has everything , don't rely on any chatgpt or ai it is worst bad and really bad
