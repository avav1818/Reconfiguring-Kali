# Reconfiguring-Kali

### What is Kali Linux?

"Kali Linux is a Debian-based Linux distribution geared towards various information security tasks, such as Penetration Testing, Security Research, Computer Forensics and Reverse Engineering." 

* Source: https://www.kali.org/ 
* Download Kali Linux: https://www.kali.org/downloads/
* Tutorial on verifying authenticity of the Kali Linux ISO image: https://technibuzz.com/how-to-verify-integrity-and-authenticity-of-kali-linux-iso-image/ 
* Note: I installed Kali Linux in Vitual Box in Windows 10
* Note: Commands to input into the terminal are `written in this format`. Follow them sequentially

### Operations to perform after installing Kali Linux. 

1. Change the default password 
* Enter `passwd`
* Enter default password `kali`
* Enter you new password and store it somewhere SECURE

![](Images/changingDefaultPassword.png)

2. Install terminal multiplexer tilix
* `sudo apt-get install tilix -y`
* After installation run tilix with `tilix` command 

![](Images/installingTilix.png)

![](Images/runningTilix.png)

![](Images/tilixMultiplexer.png)

3. Install Tor onion browser
* `sudo apt-get update`
* `sudo apt-get install tor torbrowser-launcher -y`
* Tor Browser can be found by entering "Tor" in the search browser or in: Usual Applications > Internet > Tor Browser

![](Images/installingTor.png)

![](Images/torLocation.png)

![](Images/downloadingTor.png)

![](Images/downloadingTor2.png)

![](Images/torBrowser.png)

4. Change default port for SSH from port 22, to something else more obscure
* Install SSH: `sudo apt-get install ssh -y`
* Start the SSH service: `sudo service ssh start`
* View SSH service status: `sudo service ssh status`
* Take note of your ip, next to "inet" on interface eth0 in this case: `ifconfig`
* Change to ssh directory: `cd /etc/ssh`
* View SSH configuration file details. Port will be set to 22 by default 
* `cat sshd_config`
* Open SSH configuration file with root permission and "nano" text editor
* `sudo nano sshd_config`
* Navigate to "#Port 22" within the configuration file and set it to something obscure
* Exit the nano file: "CTRL + X", "CTRL + Y", then hit enter

![](Images/ssh.png)

![](Images/ssh2.png)

![](Images/ssh3.png)

![](Images/ssh5.png)

![](Images/ssh7.png)

5. Change default SSH keys
* Navigate to directory storing ssh keys: `cd /etc/ssh`
* Create a directory to store old ssh keys: `sudo mkdir old_keys`
* Move old ssh keys into old ssh keys directory `sudo mv ssh_host_* old_keys`
* Generate new SSH keys: `sudo dpkg-reconfigure openssh-server`
* View newly generated SSH key hashes: `sudo md5sum ssh_host_*`
* View old ssh key hashes: `cd old_keys` `sudo md5sum ssh_host_*`
* Hashes will be different
* Navigate out of the old keys directory `cd ..`
* Delete the old keys directory `sudo rm -r -v old_keys`

![](Images/changingSSH.png)

![](Images/changingSSH2.png)

5. Enable postgreSQL to start at boot: `sudo systemctl enable postgresql`
* PostgreSQL is an open source relational database system that support SQL relational and JSON non-relational querying  
* More on posgreSQL: https://www.postgresql.org/about/ 

![](Images/postgreSQL.png)

6. Check installed python packages and switch to python 3 if need be
* `ls /usr/bin/python*`
* `python--version`
* `alias python=python3`
* `python --version`
* Run python from the terminal: `python`
* `alias` can be used to revert back to python2

![](Images/python3Switch.png)

7. Install git
* `sudo apt-get update`
* `sudo apt-get install git -y`
* `git --version`

![](Images/installingGit.png)

![](Images/installingGit2.png)

8. Download your first package from git, in this case "Routersploit"
* Routersploit is an exploitation framework for embedded devices
* `git clone https://github.com/threat9/routersploit`
* [Routersploit docs](https://github.com/threat9/routersploit) 
* [Routersploit example usage](https://www.youtube.com/watch?v=fgau-Dx_34o)

![](Images/routersploit.png)

![](Images/routersploit2.png)


9. Change default US keyboard layout, if necessary, and follow the instructions on the Wizard to select your preferences 
* `sudo dpkg-reconfigure keyboard-configuration`
* Restart your machine afterwards
* Source: https://askubuntu.com/questions/342066/how-to-permanently-configure-keyboard


