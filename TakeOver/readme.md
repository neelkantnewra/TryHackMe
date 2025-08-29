# Takeover — TryHackMe

Room Link: [Takeover](https://tryhackme.com/room/takeover)

---

## GoBuster (Always a Go-To Tool)

I chose to start with **GoBuster** since I’m not very familiar with `nmap` and other tools.  
My goal here was to look for any **open subdomains**.

---

### Steps:

1. **Add hostname to `/etc/hosts`**  
   - Make sure the target domain is mapped in your hosts file.

2. **Run GoBuster with DNS mode**  
   - Use the following wordlist:  
     ```
     Tools/wordlists/SecLists/Discovery/DNS
     ```
   - Example command:
     ```bash
     gobuster -m dns -u targetdomain.com -w /path/to/SecLists/Discovery/DNS/namelist.txt
     ```

3. **Experiment with different wordlists**  
   - Since this is about subdomain discovery, try multiple wordlists.  
   - I encourage you to experience the same "pain" I went through by testing various lists to ensure nothing is missed. 😅

---



 
