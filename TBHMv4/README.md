# Recon

The Bug Hunter Methodology by [Jason Haddix](https://twitter.com/jhaddix)

## [xmind](https://aur.archlinux.org/packages/xmind-2020/)

A scheme tree for the recon mindset

## Finding Seeds

- init:
	* Bug bounty programs (BugCrowd, HackerOne, Intigriti ..)
	* [CrunchBase](https://www.crunchbase.com/)
- Asn:
	* [Hurrican Electric](https://bgp.he.net/)
	* [ASNlookup](https://github.com/yassineaboukir/Asnlookup)
	* [Metabigor](https://github.com/j3ssie/metabigor)
	* [Amass](https://github.com/OWASP/Amass)
```bash
$ amass intel -asn <ASXXXX>
```
- Reverse Whois:
	* [Whoxy](https://www.whoxy.com/)
	* [DOMLink](https://github.com/vysecurity/DomLink)
- WebAppInfo
	* [BuiltWith](https://builtwith.com/)
	* GoogleFu 
```
 "<COPYRIGHT_TEXT|TERMS_PF_SERVICE|PRIVACY_POLICY>" inurl:<DOMAIN>
```
	* [Shodan](https://www.shodan.io/)
## Subdomain Enumeration

- Linked and JS Discovery
	* Target with [BurpSuite](https://portswigger.net/burp) (Filtering: Target->Scope->check "Use Advenced Scope Control"->Add Scope Rule->Host:Target IP/Domain/Keyword, 2: Site Map->R\* Bar->Check "Show Only In Scope Items", 3: Spidering, 4: Right Click on selected targets->Engagement Tools->Analyse Target (Will Export a parsed file))
	* [GoSpider](https://github.com/jaeles-project/gospider)
	* [Hakrawler](https://github.com/hakluke/hakrawler)
	* [SubDomainizer](https://github.com/nsonaniya2010/SubDomainizer) (Interesting can parse Tokens/Keys)
	* [SubScrapper](https://github.com/m8r0wn/subscraper) (Has Recursion)
- Subdomain Scrapping
	* (Infrastructure Sources, Certificate Sources, Security Sources, Search Sources)
	* Google:
```
site:twitch.tv -www.twitch.tv
site:twitch.tv -www.twitch.tv -watch.twitch.tv
site:twitch.tv -www.twitch.tv -watch.twitch.tv -dev.twitch.tv
...
```
	* [Amass](https://github.com/OWASP/Amass)/[Subfinder](https://github.com/projectdiscovery/subfinder)
```bash
$ amass enum -d <DOMAIN>
$ subfinder -d <DOMAIN> -v
```
	* [github-subdomains](https://github.com/gwen001/github-subdomains) (5 iter, Rate Limited every 6 seconds, last 10s) /[Gwendal Le Cogwic](https://github.com/gwen001)
	* [shosubgo][https://github.com/0xrod/shosubgo]
	* [bufferover.run](https://bufferover.run/dns?q=<DOMAIN>) / [MassScan](https://github.com/robertdavidgraham/masscan)
	* DefCon talk Sam Erb
- Subdomain Bruting
	* [amass](https://github.com/OWASP/Amass)
```bash
$ amass enum -brute -d <DOMAIN> -src # <- built in wordlist
$ amass enum -brute -d <DOMAIN> -rf reseolvers.txt -w bruteforce.list
```
	* [ShuffleDNS](https://github.com/projectdiscovery/shuffledns)
- Wordlists:
	* [Jason Haddix all.txt](https://gist.github.com/jhaddix/f64c97d0863a78454e44c2f7119c2a6a)
## DNS Altering
	* [altdns](https://github.com/infosec-au/altdns)

## Other

	* [masscan](https://github.com/robertdavidgraham/masscan)/[nmap](https://nmap.org/)
```bash
$ masscan -p1-65535 -iL $ipFile --max-rate 1800 -oG $outFile.log
```
	* [dnmasscan](https://github.com/rastating/dnmasscan) (for domain names port scannig)
	* [brutespray](https://github.com/x90skysn3k/brutespray) (takes nmap oG file format to scan administration protocols for default passwords)
	* [Jhaddix google dorks script](https://gist.github.com/jhaddix/1fb7ab2409ab579178d2a79959909b33)

- HTTP screenshots
	* aquatone, HTTPscreenshot, eyewitness
	* chrome, mozilla

## subdomain takeover
	* [can i take over xyz](https://github.com/EdOverflow/can-i-take-over-xyz)
	* [subover](https://github.com/Ice3man543/SubOver)
	* [nucleii subdomain takeover](https://github.com/projectdiscovery/nuclei)
## automation++
	* [interlace](https://github.com/codingo/Interlace)
	* [Tomnomnom](https://github.com/tomnomnom)
## Tiers

	* C-Tier:
<img src="https://i.gyazo.com/305f2821417d7f2b00bd88cac4a65f11.png" >
	* B-Tier:
<img src="https://i.gyazo.com/e77c4f4a9a52e8a0e939c77d5c345988.png">
	* A-Tier:
<img src="https://i.gyazo.com/4ac0d76e8b996c1d8c512080d767a2e9.png">
	* S-Tier:
<img src="https://i.gyazo.com/05cf6992f6e0658c2421fde5ea5bf273.png">

<img src="https://i.gyazo.com/df67c479b725ab1cdd1631c4cbf3fdf2.png">
