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
