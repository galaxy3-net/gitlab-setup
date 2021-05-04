# gitlab-setup

1. Create SSH key for gitlab
    1. ssh-keygen -f ~/.ssh/id_ucibootcamp
        <br />Enter passphrase x2
2. Upload the SSH Public key to gitlab
    1. Log into Gitlab
    2. Goto Account -> SSH keys
    3. Enter Title: "Laptop to Gitlab"
    4. Paste Public Key ("id_ucibootcamp.pub")
    5. Click "Add key"
3. Create ucibootcamp Config File
    1. mkdir -p ~/.ssh/config.d
    2. chmod 0700 ~/.ssh/config.d
    3. nano (vi) ~/.ssh/config.d/ucibootcamp
    ```
   Host ucibootcamp
       HostName uci.bootcampcontent.com
       User     git
       IdentityFile ~/.ssh/id_ucibootcamp
       StrictHostKeyChecking no
       UserKnownHostsFile /dev/null
       AddKeysToAgent yes
       UseKeyChain yes (only on MacOS)
   ```
4. Create Config File
    1. nano (vi) ~/.ssh/config
    ```
   Include ~/.ssh/config.d/*
   ```
   2. chmod 0644 ~/.ssh/config
7. Test Config
    1. bash-3.2$ ssh ucibootcamp
    ```
       Warning: Permanently added 'uci.bootcampcontent.com,138.197.198.248' (ECDSA) to the list of known hosts.
       PTY allocation request failed on channel 0
       Welcome to GitLab, @kirscht!
       Connection to uci.bootcampcontent.com closed.
   ```
6. Clone the Repo
    1. mkdir -p ~/repos (or repositories)
    2. cd ~/repos
    3. git clone ucibootcamp:UCI-Coding-Bootcamp/uci-irv-cyber-pt-03-2021-u-c.git
7. Test the Repository
    1. cd ~/repos/uci-irv-cyber-pt-03-2021-u-c
    2. git status    
   
