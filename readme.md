# Bitcoin Nodes

Some Bitcoin nodes are publicly available. 
One can write a tool to geo- localize those nodes, understand network topology (!!!), understand how many nodes are using TOR.

## How bitcoin clients connect to servers
- hardcoded list in software: https://github.com/bitcoin/bitcoin/tree/master/contrib/seeds
  - Bitcoin core maintained list: https://bitcoin.sipa.be/seeds.txt.gz
  - List can be generated with [bitcoin-seeder](https://github.com/sipa/bitcoin-seeder). A tutorial can be found [here](https://bitcoindev.network/bitcoin-network-statistics/)
- DNS seed: seed.bitcoin.sipa.be
```bash
 dig @8.8.8.8 seed.bitcoin.sipa.be A

; <<>> DiG 9.11.4-P2-RedHat-9.11.4-26.P2.el7_9.9 <<>> @8.8.8.8 seed.bitcoin.sipa.be A
; (1 server found)
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 20794
;; flags: qr rd ra; QUERY: 1, ANSWER: 25, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;seed.bitcoin.sipa.be.          IN      A

;; ANSWER SECTION:
seed.bitcoin.sipa.be.   3600    IN      A       188.165.244.143
seed.bitcoin.sipa.be.   3600    IN      A       153.92.93.114
seed.bitcoin.sipa.be.   3600    IN      A       37.220.109.238
seed.bitcoin.sipa.be.   3600    IN      A       93.46.80.157
seed.bitcoin.sipa.be.   3600    IN      A       96.255.215.56
seed.bitcoin.sipa.be.   3600    IN      A       67.162.69.225
seed.bitcoin.sipa.be.   3600    IN      A       3.22.120.116
seed.bitcoin.sipa.be.   3600    IN      A       185.165.168.196
seed.bitcoin.sipa.be.   3600    IN      A       107.208.177.42
seed.bitcoin.sipa.be.   3600    IN      A       3.35.166.20
seed.bitcoin.sipa.be.   3600    IN      A       3.37.69.205
seed.bitcoin.sipa.be.   3600    IN      A       178.128.97.218
seed.bitcoin.sipa.be.   3600    IN      A       73.168.103.27
seed.bitcoin.sipa.be.   3600    IN      A       3.235.196.4
seed.bitcoin.sipa.be.   3600    IN      A       3.96.190.111
seed.bitcoin.sipa.be.   3600    IN      A       138.197.180.164
seed.bitcoin.sipa.be.   3600    IN      A       94.157.2.69
seed.bitcoin.sipa.be.   3600    IN      A       149.248.7.219
seed.bitcoin.sipa.be.   3600    IN      A       13.245.27.50
seed.bitcoin.sipa.be.   3600    IN      A       85.208.71.39
seed.bitcoin.sipa.be.   3600    IN      A       3.238.134.107
seed.bitcoin.sipa.be.   3600    IN      A       120.79.173.243
seed.bitcoin.sipa.be.   3600    IN      A       5.8.18.154
seed.bitcoin.sipa.be.   3600    IN      A       161.97.141.29
seed.bitcoin.sipa.be.   3600    IN      A       5.9.28.141

;; Query time: 118 msec
;; SERVER: 8.8.8.8#53(8.8.8.8)
;; WHEN: Sat Mar 05 22:05:45 CET 2022
;; MSG SIZE  rcvd: 449

```
- To get known peers from a node, addr command is used: https://github.com/sipa/bitcoin-seeder/blob/3ef602de83a76bc95a06867d4bfc239f13992140/bitcoin.cpp#L134
- The [makeseeds.py](https://github.com/bitcoin/bitcoin/blob/master/contrib/seeds/makeseeds.py) already retrieves the ASN per IP. 

## Geolocation
- [Geoplugin](http://www.geoplugin.com/)
- [IP-API] (https://ip-api.com/)

## TODO
- Adjust the bitcoin-seeder to dump the addrlist of each node => Helps to create relationships between nodes
- Import to a GraphDB or other alternatives
- Classify manually high degree nodes (Mining pool, exchange platform, etc.)

## Resources
- https://developer.bitcoin.org/devguide/p2p_network.html
- https://github.com/sipa/bitcoin-seeder
- https://www.cs.umd.edu/projects/coinscope/coinscope.pdf
