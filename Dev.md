# This is an example of the development environment setup. This document is valid only for a company or a holding. **This document is not for EVERYONE**.

---

<details>
  <summary>BEFORE INSTALLATION</summary>
  
  - If this is not your first installation, make sure to backup ~/.ssh folder to be restored later. You can zip it and upload it to your google drive storage.
  
</details>

---

<details>
  <summary>OS</summary>
  

- Ubuntu
  - Only 22.04 LTS
  - Only from ubunto.com
  - Bootable image
    - using [Startup Disk Creator](https://ubuntu.com/tutorials/create-a-usb-stick-on-ubuntu#3-launch-startup-disk-creator)
    - or using [balenaEtcher](https://ubuntu.com/tutorials/install-ubuntu-desktop#3-create-a-bootable-usb-stick)
  - Boot
  - Choose **Install Ubuntu**
    - Select English (US)
  - Keyboard layout
    - Enlish (US)
  - DO NOT Connect to WiFi
    - Reason: faster installation and async update after installation
  - Minimal installation
    - Make sure no box is selected
  - Erase disk and install Ubuntu
    - Always be ready to lose your machine
    - Advanced features
      - None
  - Press **Install Now**
    - Press **Continue**
  - Where are you?
    - Choose Tehran
    - Press **Continue**
  - Computer name
    - YourNamePc or YourNameLaptop
    - Choose a simple password (you will be asked for it frequently)
      - Preferably choose 100 as your password
    - **DO NOT** choose auto-login
      - If you choose auto-login, you will encouner *keyring* later. To disable auto-login later:
        - Settings
        - User
        - Unlock
        - disable Automatic Login
  - **DO NOT** set up **Livepatch**
    - Hit **Next**
  - **DO NOT** help Ubuntu
    - Select **No, don't send system info**
  - Privacy (Location Services)
    - Up to you
  - Remove everything from the left bar
  - **DO NOT** install any other languages
    - Just English & Persian
    - **DO NOT** change defaults
  - Change culture
    - Settings
    - Region & Language
    - Format
    - English (United States)
  - todo: DO NOT DO THIS YET
    - [Enable root](https://askubuntu.com/questions/1192471/login-as-root-on-ubuntu-desktop) and login as root always (This decision is explained [here](https://nefcanto.ir/dev-circle/philosophy/why-root))
  
</details>

---

- Connect to WiFi
- Install VPN and connect to it (in case of doubt, ASK)
- Update Ubuntu (using VPN)
  - Settings
  - Software Update
- Install software using script
  - `sudo mkdir /Temp`
  - `sudo chmod 777 /Temp`
  - `cd /Temp`
  - `wget yun.ir/s9oj9e -O Setup`
  - `sudo chmod 777 Setup`
  - `sudo ./Setup`

- **DO NOT** install any other extension on VS Code
  - In case you need something, talk to the team


- Wireshark
  - `sudo add-apt-repository universe`
  - `sudo apt install wireshark`
  - Hit `Yes`
  - `sudo dpkg-reconfigure wireshark-common`
  - `sudo chmod +x /usr/bin/dumpcap`
  - Add this to `~/.bashrc`
  - `export SSLKEYLOGFILE=~/.ssl-key.log`
  - `touch ~/.ssl-key.log`
- Docker
  - Login
    - `docker login`
  - In case of permission denied
    - test with `sudo` and make sure it works
    - if it works, run these commands
      - `sudo gpasswd -a $USER docker`
      - `newgrp docker`
      - `sudo groupadd docker`
      - `sudo usermod -aG docker ${USER}`
      - `sudo usermod -aG docker $USER`

- Git 
  - Restore `.ssh` directory, or
  - Generate keys and add your public key to GitHub 
    - Open terminal 
    - ssh-keygen -t ed25519 -C "your-email" 
    - Enter 3 times 
      - Accept default filename 
      - Empty password 
      - Empty password, again 
    - GitHub 
      - Settings 
      - SSH and GPG keys 
      - New SSH Key 
      - Copy/paste your public key there 
        - Using Files 
        - Go to the home folder 
        - Show hidden files 
        - .ssh folder 
        - id_ed25519.pub 
        - Right-click, open with the Text Editor, then copy 
  - Introduce yourself to git 
    - `git config --global user.email "your-email-of-github-here"` 
    - `git config --global user.name "your name here"`
  - Login into GitHub Container Registry
    - `docker login ghcr.io`
    - username
    - package reading personal access token
- Configuration
  - Add these to favorites, in order
    - Files
    - Chrome
    - VS Code
    - Terminal
    - Editor
- Chrome
  - Make default
    - On the first run, it asks for it
  - Do not send crash reports
  - Sign in
  - Extensions
    - JSONView
    - Grammarly
    - React Developer Tools
- VS Code
  - Turn on sync (using GitHub)
  - Word wrap
    - Files => Preferences => Settings
    - Search for “word wrap”
    - Select “on” from the dropdown
- Root
  - `sudo mkdir -p /root/.ssh`
  - `sudo ln -f -s ~/.ssh/id_ed25519 /root/.ssh/id_ed25519`
  - `sudo ln -f -s ~/.ssh/id_ed25519.pub /root/.ssh/id_ed25519.pub`
  - `sudo ln -f -s ~/.ssh/known_hosts /root/.ssh/known_hosts`

* Development
  - For each company (top-level URL path segment in GitHub for example), create a directory in / (root). For example,  
    `mkdir /HolismHolding`.
    - Make sure the name maps the URL segment or the company name
  - Give that folder full permission so that all applications would work without bothering your development with `sudo` stuff:  
    `sudo chmod -R 777 /HolismHolding`
  - Only [use SSH to connect to GitHub](https://www.freecodecamp.org/news/how-to-fix-git-always-asking-for-user-credentials/).

---

# Arguments

- Pros
  - Maximum level of consistency across the entire organization or holding
  - Drastically facilitates cooperation and teamwork
  - Reduces costs notably
  - Increases efficiency
    - Not at the cost of effectiveness
- Cons
  - Limits employee freedom
  - Makes the recruitment process more difficult
  - Can be regarded as a form of technocratic dictatorship
