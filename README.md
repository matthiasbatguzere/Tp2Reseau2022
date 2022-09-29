I. Setup IP


🌞 Mettez en place une configuration réseau fonctionnelle entre les deux machines

Les deux IPs choisies, en précisant le masque:
              Ip de ma machine -> 192.168.0.2/26
              Ip de la seconde machine -> 192.168.0.1/26
              
L'adresse de réseau -> 192.168.0.0

L'adresse de broadcast -> 192.168.0.63
              
🌞 Prouvez que la connexion est fonctionnelle entre les deux machines

```
PS C:\Windows\system32> ping 192.168.0.1

Envoi d’une requête 'Ping'  192.168.0.1 avec 32 octets de données :
Réponse de 192.168.0.1 : octets=32 temps=2 ms TTL=128
Réponse de 192.168.0.1 : octets=32 temps=1 ms TTL=128
Réponse de 192.168.0.1 : octets=32 temps=1 ms TTL=128
Réponse de 192.168.0.1 : octets=32 temps=1 ms TTL=128

Statistiques Ping pour 192.168.0.1:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 1ms, Maximum = 2ms, Moyenne = 1ms
```

🌞 Wireshark it

Le ping que l'on recoit est une request 
Le ping que l'on recoit est une replie

🦈 PCAP qui contient les paquets ICMP qui vous ont permis d'identifier les types ICMP

![fichierwire](wiresharktp2.pcapng)

II. ARP my bro


🌞 Check the ARP table
```
PS C:\Windows\system32> arp -a
```
🌞 Manipuler la table ARP

🌞 Wireshark it

🦈 PCAP qui contient les trames ARP


II.5 Interlude hackerzz


III. DHCP you too my brooo


🌞 Wireshark it

🦈 PCAP qui contient l'échange DORA


IV. Avant-goût TCP et UDP



🌞 Wireshark it

🦈 PCAP qui contient un extrait de l'échange qui vous a permis d'identifier les infos
