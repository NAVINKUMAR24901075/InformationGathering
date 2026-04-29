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


## Finding IP address:
ping command is available on Windows as well as on Linux OS. Following is the example to find out the IP address of facebook.com.

## Finding Hosting Company
get further detail by using ip2location.com website.
##output

<img width="1898" height="1028" alt="image" src="https://github.com/user-attachments/assets/95887a61-9fce-4207-842d-1f0732e245b4" />


## History of the website:

https://web.archive.org/

## output

<img width="1899" height="1036" alt="image" src="https://github.com/user-attachments/assets/b737ed53-5513-4253-bd59-788f6a7c5fde" />


# Webserver Fingerprinting:

## Netcat:

sudo traceroute gov.uk 80
GET / HTTP/1.1
Host: example.com

## Output

<img width="603" height="557" alt="image" src="https://github.com/user-attachments/assets/9fc53992-9a6e-4ab2-b8fc-4a24971d8f7d" />


## nmap:

nmap gov.uk

###output

<img width="734" height="236" alt="image" src="https://github.com/user-attachments/assets/f3b17f73-7e8c-4bb2-8f87-1e6480a770f8" />


## Whatweb

whatweb gov.uk

### output

<img width="1101" height="311" alt="image" src="https://github.com/user-attachments/assets/c8325d1b-2549-4217-a5ac-7d02c53f13bd" />


## httprint

### output

<img width="901" height="804" alt="image" src="https://github.com/user-attachments/assets/216359bf-51aa-4cce-99f7-f6a1e714b1d9" />



# Tracing the Location

TCP Traceroute:
sudo traceroute -T www.gov.uk

## output

<img width="686" height="88" alt="image" src="https://github.com/user-attachments/assets/42a447e8-31d6-4d71-9c5f-d0bb49db5945" />


## UDP Traceroute:

sudo traceroute -U www.gov.uk

## output

<img width="658" height="555" alt="image" src="https://github.com/user-attachments/assets/691ee23e-5ab8-4f54-99a9-8ffc3a8b5a93" />


## ICMP Traceroute:

sudo traceroute -I www.gov.uk

## output

<img width="651" height="641" alt="image" src="https://github.com/user-attachments/assets/9fbeeb7c-1f77-4de0-9109-740197f7dbcf" />


## RESULT:
The information gathering techniques tools/procedure were  identified successfully
