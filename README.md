# InformationGathering
Information Gathering Techiques

# To perform information gathering techniques

# AIM:

To perform information gathering techniques using kali linux 

## STEPS:

### Step 1:

Install kali linux either in partition or virtual box or in live mode

### Step 2:

Investigate on the various categories of tools as follows:

### Step 3:
Open terminal/browser and try execute necessary commands/use url to perform information gathering

## Pen Test Tools Categories:  

Following Categories of pen test tools are identified for information gathering:

Footprinting is a part of the reconnaissance process which is used for gathering possible information about a target computer system or network.
http://www.whois.com/whois website to get detailed information about a domain name information including its owner, its registrar, date of registration, expiry, name server, owner's contact information, etc.

## OUTPUT:

<img width="1904" height="1032" alt="image" src="https://github.com/user-attachments/assets/41bce254-400e-4cb1-8793-dc16c9ea9298" />

#### Summary

🔹 Domain Information
Domain Name: gov.uk
Status:
Server update prohibited
Server delete prohibited
Server transfer prohibited
(This means the domain is highly protected and cannot be modified, deleted, or transferred easily.)
Name Servers:
dns1.nic.uk
dns2.nic.uk
dns3.nic.uk
dns4.nic.uk
nsa.nic.uk
nsb.nic.uk
nsc.nic.uk
nsd.nic.uk
🔹 Registrar Information
Registrar: Nominet UK
IANA ID: NOMINET
Official Website: www.nominet.uk
Abuse Contact:
Email: abuse@nominet.uk
Phone: +44 1865 332244
🔹 Key Understanding
The domain gov.uk is an official government domain of the United Kingdom.
It is tightly secured, which is why all modification actions are restricted.
Managed by Nominet UK, the official registry for .uk domains.


## Finding IP address:
ping command is available on Windows as well as on Linux OS. Following is the example to find out the IP address of facebook.com.

## Finding Hosting Company
get further detail by using ip2location.com website.
##output

<img width="1898" height="1028" alt="image" src="https://github.com/user-attachments/assets/95887a61-9fce-4207-842d-1f0732e245b4" />

#### Summary

The image is a screenshot of an IP lookup results page from the IP2Location website. It shows detailed information for the IP address 151.101.192.144.
At the top, there’s a search bar where the IP address has been entered, along with a “Lookup” button. Below that, the page is divided into two main sections: Geolocation Data on the left and Proxy Data on the right.

Key details from the Geolocation Data section:
Country: United States
Region: California
City: San Francisco
Coordinates: Approximately 37.7749, -122.4194
ISP: Fastly, Inc.
Domain: fastly.com
ZIP Code: 94107
Time Zone: America/Los_Angeles
Usage Type: CDN (Content Delivery Network)
Address Type: Anycast
Category: Data Centers


Key details from the Proxy Data section:
Proxy Detected: No (not an anonymous proxy)
Proxy Country/Region/City: United States, California, San Francisco
Proxy ISP: Fastly, Inc.
Proxy Domain: fastly.com
Usage Type: CDN
Proxy Type: DCH (Data Center/Hosting)
ASN: AS54113 Fastly Inc.
Fraud Score: 3 (relatively low risk)
Overall interpretation:

This IP address belongs to Fastly, a well-known content delivery network provider. Rather than identifying a specific individual or device, the IP is associated with a data center infrastructure used to deliver web content efficiently.


## History of the website:

https://web.archive.org/

## output

<img width="1899" height="1036" alt="image" src="https://github.com/user-attachments/assets/b737ed53-5513-4253-bd59-788f6a7c5fde" />

#### Summary

The page displays archived data for www.gov.uk
indicating it has been saved over 914,000 times between May 2002 and April 2026.
A MIME-type breakdown shows that most captured content is HTML (text/html), followed by images, CSS, JavaScript, and other file types like XML, PDFs, and fonts.
A pie chart visually emphasizes that HTML content dominates the archive.
A bar chart at the bottom illustrates growth over time in:
Total captures
Unique URLs
New URLs added each year
The data shows a significant increase in archived content starting around the early 2010s, reflecting expansion of the website.


# Webserver Fingerprinting:

## Netcat:

sudo traceroute gov.uk 80
GET / HTTP/1.1
Host: example.com

## Output

<img width="603" height="557" alt="image" src="https://github.com/user-attachments/assets/9fc53992-9a6e-4ab2-b8fc-4a24971d8f7d" />

#### Summary

This screenshot shows a traceroute command run from a Kali Linux terminal targeting gov.uk on port 80.
The destination IP resolves to 151.101.128.144.
The first hop (local gateway: 10.0.2.2) responds with very low latency.
All subsequent hops (2–30) return * * *, meaning:
Intermediate routers are not responding to traceroute probes.
This is commonly due to firewalls, ICMP filtering, or network security policies.
Interpretation:
The route to the server is largely hidden, likely intentionally, which is typical for well-secured infrastructure.

## nmap:

nmap gov.uk

###output

<img width="734" height="236" alt="image" src="https://github.com/user-attachments/assets/f3b17f73-7e8c-4bb2-8f87-1e6480a770f8" />

#### Summary

This screenshot shows an nmap scan of gov.uk.
Target IP: 151.101.64.144
Host is up and reachable with low latency (~0.026s).
Open ports:
80/tcp → HTTP
443/tcp → HTTPS
998 ports are filtered, meaning they do not respond (likely blocked by firewall).
Multiple IPv4 and IPv6 addresses are associated with the domain.
Interpretation:
The server exposes only standard web ports, indicating a minimal attack surface and strong network filtering.

## Whatweb

whatweb gov.uk

### output

<img width="1101" height="311" alt="image" src="https://github.com/user-attachments/assets/c8325d1b-2549-4217-a5ac-7d02c53f13bd" />

#### Summary

This screenshot shows a whatweb scan identifying technologies used by gov.uk.
The site redirects from HTTP to HTTPS (301 Moved Permanently).
Final response: 200 OK
Key technologies detected:
Varnish (caching/proxy layer)
nginx (web server)
Headers indicate:
Strong security policies (HSTS, X-Frame-Options, XSS protection, etc.)
Use of Fastly CDN infrastructure
Page title confirms: GOV.UK
Country detected: United States (likely due to CDN edge servers, not actual hosting origin)
Interpretation:
The website uses a modern, secure web stack with CDN caching, reverse proxies, and hardened security headers.


## httprint

### output

<img width="901" height="804" alt="image" src="https://github.com/user-attachments/assets/216359bf-51aa-4cce-99f7-f6a1e714b1d9" />

#### Summary

This screenshot shows the help/usage output of the httpprint tool run on a Kali Linux terminal.
httpprint is a web server fingerprinting tool used to identify server types based on HTTP responses.
The command attempted: httpprint -h georgia.com -s
The output mainly displays:
Tool version (v0.301 beta)
Usage syntax and parameters
Options for input/output formats (HTML, CSV, XML)
Configuration settings like timeout, retries, threads, and SSL detection
Interpretation:
Instead of scanning, the tool displayed its help menu, likely due to missing or incorrect arguments.


# Tracing the Location

TCP Traceroute:
sudo traceroute -T www.gov.uk

## output

<img width="686" height="88" alt="image" src="https://github.com/user-attachments/assets/42a447e8-31d6-4d71-9c5f-d0bb49db5945" />


#### Summary

This screenshot shows a traceroute using TCP SYN packets to www.gov.uk
Target IP: 151.101.156.144
Only 1 hop is shown, which is the destination itself.
Response times are around 60–67 ms
Interpretation:
The trace reaches the destination immediately, likely due to:
CDN edge routing (e.g., Fastly)
Network configuration that skips intermediate hop visibility


## UDP Traceroute:

sudo traceroute -U www.gov.uk

## output

<img width="658" height="555" alt="image" src="https://github.com/user-attachments/assets/691ee23e-5ab8-4f54-99a9-8ffc3a8b5a93" />

#### Summary

This screenshot shows a UDP-based traceroute to www.gov.uk
First hop: local gateway (10.0.2.2)
All subsequent hops show * * * (no response)
Interpretation:
UDP probes are being blocked or ignored after the first hop, indicating:
Firewall filtering
Network security restrictions


## ICMP Traceroute:

sudo traceroute -I www.gov.uk

## output

<img width="651" height="641" alt="image" src="https://github.com/user-attachments/assets/9fbeeb7c-1f77-4de0-9109-740197f7dbcf" />


#### Summary

This screenshot contains two traceroute attempts:
ICMP (-I)
Directly reaches the destination in 1 hop
Response times around 52–60 ms
Default traceroute
First hop (local gateway) responds
All remaining hops show * * *
Interpretation:
ICMP traceroute succeeds quickly (likely optimized routing via CDN)
Default traceroute (UDP-based) is mostly blocked
Confirms restricted network visibility and strong filtering

## RESULT:
The information gathering techniques tools/procedure were  identified successfully
