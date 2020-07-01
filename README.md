TL;TR; [@jhaddix](https://github.com/jhaddix) bug hunter methodology v4 
Youtube:
https://www.youtube.com/watch?v=p4JgIu1mceI


# Finding Seeds/Roots
## Acquisition 
```
crunchbase
google.com
```

## ASN Enumeration
```
bgp.ne.net
echo 'tesla' | metabigor net --org -v 
amasss intel -asn 46489
```

## Reverse WHOIS
```
http://api.whoxy.com/?key=APIkeyHERE&reverse=whois&name=Twich+Hostmaster
python ./domLink.py -d vip.com -o vip.txt
```
## Ad/Analytucs Relationships 
```
builtwith.com
```
## Shodan
```
https://www.shodan.io/search?query=twitch.tv
```

#  Finding Subdomains
## Linked Discovery
### Gospider
[https://github.com/jaeles-project/_gospider](GoSpider)
```
gospider -s https://twitch.tv
```
### Hakcrawler
[https://github.com/hakluke/hakrawler](https://github.com/hakluke/hakrawler)

```
gospider -s "https://google.com/" -o output -c 10 -d 1
```
### Sumbdomainizer
[https://github.com/nsonaniya2010/SubDomainizer](https://github.com/nsonaniya2010/SubDomainizer)
```
python3 SubDomainizer.py -u http://www.example.com
```
### Subscraper
[https://github.com/m8r0wn/subscraper](https://github.com/m8r0wn/subscraper)
```
subscraper --enum 2 example.com
```
## Subdomain Scraping
### Google
```
site:twitch.tv -www.twitch.tv
```
### Amass
```
amass -d twitch.tv
```
### Subfinder v2
[https://github.com/projectdiscovery/subfinder](https://github.com/projectdiscovery/subfinder)
```
subfinder -d hackerone.com -v
```

### github-subdomains

[https://github.com/gwen001/github-search/blob/master/github-subdomains.py](https://github.com/gwen001/github-search/blob/master/github-subdomains.py)

```
python3 github-subdomain.py -t "$GIT_TOKEN" -d twitch.tv 
```
### shosubgo
[https://github.com/incogbyte/shosubgo](https://github.com/incogbyte/shosubgo)
```
go run main.go -d target.com -s YourAPIKEY
```
## Subdomain Bruteforce
### Amass
```
amass enum -brute -d twitch.tv -src 
amass enum -brute -d twitch.tv -rf resolvers.txt -w bruteforce.list
```
## shuffleDNS
[https://github.com/projectdiscovery/shuffledns](https://github.com/projectdiscovery/shuffledns)
```
shuffledns -d hackerone.com -w words.txt -r resolvers-excellent.txt
```

## Subdomain wordlist
[https://github.com/assetnote/commonspeak2](https://github.com/assetnote/commonspeak2)

# Other
## Portscan
### Masscan
```
masscan -p1-65535 -iL $ipFile --max-rate 1800 -oG $outPut.log
```
### dnmasscan
Masscan wrapper which resolve hostnames.
```
dnmasscan example.txt dns.log -p80,443 -oG masscan.log
```
## Servicescan
### brutespray
[https://github.com/x90skysn3k/brutespray](https://github.com/x90skysn3k/brutespray)
masscan-> nmap service scan -oG -> brutespray
```
python brutespray.py --file nmap.gnmap
```
### Github dorking
[https://www.youtube.com/watch?v=l0YsEk_59fQ](https://www.youtube.com/watch?v=l0YsEk_59fQ)

## Screenshooting
Eyewitness
Aquatone
httpscreenshot

## Subdomain Takeover
[https://github.com/EdOverflow/can-i-take-over-xyz](https://github.com/EdOverflow/can-i-take-over-xyz)
### SubOver
[https://github.com/Ice3man543/SubOver](https://github.com/Ice3man543/SubOver)
```
SubOver -l subdomains.txt -v
```
### nuclei
[https://github.com/projectdiscovery/nuclei](https://github.com/projectdiscovery/nuclei)
```
nuclei -l urls.txt -t files/git-core.yaml -o results.txt
```

# Rest
haddix/tbhm/blob/master/v4/all2.txt
[https://github.com/AdmiralGaust/bountyRecon](https://github.com/AdmiralGaust/bountyRecon)
[https://github.com/offhourscoding/recon](https://github.com/offhourscoding/recon)
[https://github.com/venom26/recon](https://github.com/venom26/recon)
[https://github.com/nahamsec/lazyrecon](https://github.com/nahamsec/lazyrecon)
