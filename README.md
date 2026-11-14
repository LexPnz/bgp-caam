# BGP Antifilter Prefixes
[English](README.md) | [Русский](README.ru.md)

Optimized BGP prefix lists generated based on [antifilter.download](https://antifilter.download/), with additional domain and ASN-based adjustments.

The exported prefix lists are intended for network routing and filtering using BGP-compatible routers and routing software. 

## Files

| File | Description |
|---|---|
| [`networks.txt`](networks.txt) | Plain IPv4 CIDR prefix list, one prefix per line |
| [`mikrotik.rsc`](mikrotik.rsc) | MikroTik RouterOS firewall address-list import script |

## Additional Domains

The following domains have been added:

- `rutracker.org`
- `nnmclub.to`
- `4pda.to`
- `nextdns.io`
- `stackoverflow.com`
- `mobileproxy.space`

## Additional ASNs

The following Apple networks have been added:

| ASN | Organization |
|---:|---|
| AS714 | APPLE |
| AS6185 | APPLE |

## Excluded Russian ASNs

The following ASNs have been excluded from the Russian prefix list:

| ASN | Organization |
|---:|---|
| AS201012 | Avito LLC |
| AS204720 | CDNetworks Global Cloud Network |
| AS210756 | EdgeCenter LLC |
| AS211609 | OKKO |
| AS29182 | RU-JSCIOT |
| AS41718 | VITRINA TV |
| AS47541 | VK SPB |
| AS48018 | FORNEX |
| AS51115 | HLL |
| AS57363 | CDNVIDEO |
| AS57724 | DDOS GUARD |

## Usage

### Download prefix list

```bash
wget -O networks.txt \
  https://raw.githubusercontent.com/LexPnz/bgp-caam/main/networks.txt
  ```
  
  ### MikroTik RouterOS
  
  ```routeros
  /tool fetch url="https://raw.githubusercontent.com/LexPnz/bgp-caam/main/mikrotik.rsc" dst-path=mikrotik.rsc
  /import file-name=mikrotik.rsc
  ```
  
  ## Updates
  
  Prefix lists are generated automatically from BIRD routing tables and published to this repository.
  
  Both export formats are generated from the same prefix dataset.
  
  ## Disclaimer
  
  This project provides routing prefix lists based on external sources and additional filtering rules.
  
  Prefix ownership, routing announcements and network allocations may change over time. Use the lists at your own discretion and verify their contents before applying them to production routing infrastructure.