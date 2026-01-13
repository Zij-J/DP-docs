# Using SSH for Git Remote 
Last Modified: 2025-11-11, Zij-J

Two Problems:

> The authenticity of host 'github.com (20.27.177.113)' can't be established.
ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])?

**Ans Ref**: [StackOverflow](https://stackoverflow.com/questions/47707922/error-the-authenticity-of-host-github-com-cant-be-established-rsa-key-finge)  
SSH(Secure Shell) Protocol just want to ensure github is github:   
1. Check `ED25519 key fingerprint is SHA256:+DiY3wvvV6TuJJhbpZisF/zLDA0zPMSvHdkr4UvCOqU.` is in [github's list](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/githubs-ssh-key-fingerprints), if is, `yes` it.
2. `~\.ssh` will add github in `known_hosts` automatically.
3. Done! 

> git@github.com: Permission denied (publickey).

**Ans Ref**: [Github Docs 1](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent), [Github Docs 2](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account) & [StackOverflow](https://stackoverflow.com/questions/2643502/how-to-solve-permission-denied-publickey-error-when-using-git) & [IT邦](https://ithelp.ithome.com.tw/articles/10205988)  
Using SSH need to 
1. `ssh-keygen -t ed25519 -C "your_email@example.com"`
    - `-t`: **type** of key to generate
    - `-C`: **Comment** of the key (multi-key management) won't affect key (maybe)
    - `your_email@example.com`: Change to your email!
2. `Enter file in which to save the key (C:\Users\Zij-J/.ssh/id_ed25519):` Press Enter. Gen file at `C:\Users\Zij-J/.ssh/id_ed25519`
3. `Enter passphrase (empty for no passphrase):` Being lazy. Press Enter.
4. `start-ssh-agent`, will `Identity added: /c/Users/Zij-J/.ssh/id_ed25519` to `ssh-agent` automatically by [StackOverflow](https://stackoverflow.com/questions/18683092/how-to-run-ssh-add-on-windows)
5. `cat ~/.ssh/id_ed25519.pub | clip` to copy public key to clipboard 
    - `cat`: concatenate
6. Profile Icon `>  Setting > SSH and GPG keys > New SSH key` Name it and add it.
7. Done! Can `push/clone` with SSH now~

