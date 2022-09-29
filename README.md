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

Utilisez une commande pour afficher votre table ARP:
```
PS C:\Windows\system32> arp -a
```
Déterminez la MAC de votre binome depuis votre table ARP:
```
 192.168.0.1           10-82-86-0b-15-00
```
Déterminez la MAC de la gateway de votre réseau:
```
 10.33.19.254          00-c0-e7-e0-04-4e
```

🌞 Manipuler la table ARP

utilisez une commande pour vider votre table ARP:
```
PS C:\Windows\system32> arp -d
```
Prouvez que ça fonctionne en l'affichant et en constatant les changements, ré-effectuez des pings, et constatez la ré-apparition des données dans la table ARP:
```
Interface : 192.168.0.2 --- 0x7
  Adresse Internet      Adresse physique      Type
  192.168.0.1           10-82-86-0b-15-00     dynamique
  192.168.0.63          ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  255.255.255.255       ff-ff-ff-ff-ff-ff     statique
  ```

🌞 Wireshark it

🦈 PCAP qui contient les trames ARP

![sharkbroadcast](arpbroadcast.pcapng)

III. DHCP you too my brooo


🌞 Wireshark it

🦈 PCAP qui contient l'échange DORA

![dora](dora.pcapng)


IV. Avant-goût TCP et UDP


🌞 Wireshark it

🦈 PCAP qui contient un extrait de l'échange qui vous a permis d'identifier les infos
