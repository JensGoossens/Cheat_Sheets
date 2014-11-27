# DNS-server
Troubleshooting van de DNS-server
 
 Functie| Commando
 ----------| -------------------
 Dit geeft een lijst van packages waarin commando dig zit | ```yum provides *bin/dig```
 Controleren van de DNS instellingen | ```nslookup```
 Vinden van ip-adres van een domein | ```nslookup "naam van domein (bv. yahoo.com)"```
 Reverse domain lookup | ```nslookup "ip-adres"```
 Debug mode enablen | ```nslookup -debug "naam van domein"```
 Poortnummer veranderen van DNS (kan helpen) | ```nslookup -port "poortnummer" "domeinnaam" (vb nslookup -port 54 google.com)```
 Flush DNS cache | ```/etc/rc.d/init.d/nscd restart``` OF ```/etc/init.d/nscd restart```
 Dig, een tool om de DNS server te ondervragen | ```dig "domeinnaam"```
 http://g33kinfo.com/info/archives/1548
 
 # BIND server voor troubleshooting?
 
  Functie| Commando
 ----------| -------------------
 BIND server starten | ```service named start```
 BIND server stoppen | ```service named stop```
 BIND server restarten | ```service named restart```
 BIND server reloaden | ```service named reload```
 BIND server status | ```service named status```
 
 
# Samba-server
Bron: http://www.samba.org/samba/docs/using_samba/ch12.html
Hieronder elk commando te overlopen bij problemen, indien een error bij een commando 
=> link voor oplossingen

Zaken te overlopen : 

- Samba logs
  samba_directory /var/smbd.log ;
  samba_directory /var/nmbd.log

- Fault tree : problemen met install en configureren
   adressering testen: ping 127.0.0.1
                       ping localhost
   tcp testen: ftp server
   server daemons testen : eerst logs checken => 'smbd version number started' moet er staan.
   processen checken : ps ax of ps -ef
   registratie daemons : netstat -a  => nakijken voor : netbios, 137, of 139
   simpele test smbd: echo "hello" | telnet localhost 139 => indien 'connected' => er luistert een daemon 
   testparm 
   
  Als je weet dat de servers draaien: smb.conf file in /usr/local/samba/lib plaatsen
  smbclient -L localhost -U%  testen op errors
  smbclient '\\server\temp'  testen op errors
  
  Netwerk testen met nmblookup : nmblookup -d 2 '*' 
  
  Problemen met DNS : zie DNS cheat-sheet

   
- Unix utilities
 trace, tcpdump, Ethereal
- Samba test utilities

- Documentation and FAQs
http://www.samba.org/

 
