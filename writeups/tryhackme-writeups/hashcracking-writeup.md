Hash Cracking - Format Enumeration (TryHackMe Labs)

While cracking a Windows hash with Jumbo John, the tool returned a list of multiple possible formats instead of cracking automatically. 
Rather than retrying it manually, I tried a Bash loop to test all suggested hash formats in one go.

  for f in nt raw-md4 mscash mscash2 raw-md5; do echo "========== Trying $f =========="; john --format=$f --wordlist=/usr/share/wordlists/rockyou.txt ntlm.txt; done

We can also add && break to stop on the first successful crack. 
A Small automation while learning however it's the kind of thing that matters when you're dealing with multiple unknown formats under time pressure.
