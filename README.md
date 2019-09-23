# iptools
Bash tools for querying your computer's publically-visible IP and DNS server from the command line.

## 1. getip
Uses the Duckduckgo search engine to get the public IP of an internet-connected computer
### Usage
> getip
### Example Output
> XXX.XXX.XXX.XXX
> City, State, Country (CC)
### Installation
No special installation required, just copy or symlink the scripts somewhere on your path (e.g. /usr/local/bin).

## 2. dnsleak
This tool is used to detect both the public IP and the publically-visible DNS server using a combination of myip.opendns.com and akahelp.netget. It then uses the whois and geoiplookup tools to load geographical information about the two IPs. The two results are combined and all available fields are displayed. 
As the name suggests, this tool is usefull to detect if your VPN has a DNS leak. Websites can query your DNS server to get an idea of your geographic location. For example: https://www.dnsleaktest.com

### Usage
> dnsleak
### Example Output
```
Getting Whois Information for IP: XXX.XXX.XXX.XXX  
Getting Whois Information for IP: NNN.NNN.NNN.NNN 
Getting GeoIP Information for IP: XXX.XXX.XXX.XXX 
Getting GeoIP Information for IP: NNN.NNN.NNN.NNN 
Using combined geoip and whois for public IP
Using combined geoip and whois for public DNS
Public IP: XXX.XXX.XXX.XXX 
        Address: ??? 
        Organization: ??? 
        City: ???
        Postal: ???
        State/Province: ???
        Country: ???
Local DNS Server (/etc/resolv.conf): 127.0.2.1
Public DNS Server: NNN.NNN.NNN.NNN
        Address: ??? 
        Organization: ??? 
        Country: ???
```

### Installation
dnsleak requires either whois or geoiplookup to be installed (or both!). 
Example (Ubuntu):
```
sudo apt-get install whois
sudo apt-get install geoip-bin 
```
