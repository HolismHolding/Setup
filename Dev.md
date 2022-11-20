# This is an example of the development environment setup. This document is valid only for a company or a holding. **This document is not for EVERYONE**.

## TODO: Use preseeding

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
  - Computer name = local
  - User name = user
  - Set password to 100 (you will be asked for it frequently)
  - **DO NOT** choose *Log in automatically*
  - **CHOOSE** Require my password to login
  - Wait for installation
  - **DO NOT** help Ubuntu
    - Select **No, don't send system info**
  - Privacy off
  - Click Done (don't worry about progress)
  
</details>

---

- Connect to WiFi
- Install software using script
  - `sudo mkdir /Temp`
  - `sudo chmod 777 /Temp`
  - `cd /Temp`
  - `wget https://raw.githubusercontent.com/HolismHolding/Setup/main/Dev -O Setup`
  - `sudo chmod 777 Setup`
  - `sudo ./Setup`

- **DO NOT** install any other extension on VS Code
  - In case you need something, talk to the team

- Update Ubuntu (using VPN)
  - Settings
  - Software Update

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
    - `ssh-keygen -t ed25519 -C "your-email"`
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
- Chrome
  - Do not send crash reports
  - Sign in
  - Extensions
    - JSONViewer
    - Grammarly
    - React Developer Tools
- VS Code
  - Turn on sync (using GitHub)
  - Word wrap
    - Files => Preferences => Settings
    - Search for “word wrap”
    - Select “on” from the dropdown

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
