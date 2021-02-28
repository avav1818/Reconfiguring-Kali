# Reconfiguring-Kali

### What is Kali Linux?

"Kali Linux is a Debian-based Linux distribution geared towards various information security tasks, such as Penetration Testing, Security Research, Computer Forensics and Reverse Engineering." 

* Source: https://www.kali.org/ 
* Download Kali Linux: https://www.kali.org/downloads/
* Tutorial on verifying authenticity of the Kali Linux ISO image: https://technibuzz.com/how-to-verify-integrity-and-authenticity-of-kali-linux-iso-image/ 
* Note: I installed Kali Linux in Vitual Box in Windows 10

### Operations to perform after installing Kali Linux. 

1. Change the default password 
* Enter `psswd` command followed the default password `kali` and then enter your NEW password

2. Install terminal multiplexer tilix
* `sudo apt-get install tilix -y`
* After installation run tilix with `tilix` command 

3. Install Tor onion browser
* `sudo apt-get update`
* `apt-get install tor torbrowser-launcher -y`
* Tor browser application will then be found in the Usual Applications 

