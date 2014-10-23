# DNS-server
Troubleshooting van de DNS-server
 
 Functie| Commando
 ----------| -------------------
 Controleren van de DNS instellingen | ```nslookup```
 Vinden van ip-adres van een domein | ```nslookup "naam van domein (bv. yahoo.com)"```
 Reverse domain lookup | ```nslookup "ip-adres"```
 Debug mode enablen | ```nslookup -debug "naam van domein"```
 DNS registreren | ```ipconfig /registerdns```
 DNS instellingen tonen | ```ipconfig /displaydns```
 Poortnummer veranderen van DNS (kan helpen) | ```nslookup -port "poortnummer" "domeinnaam" (vb nslookup -port 54 google.com)```
 Flush DNS cache | ```/etc/rc.d/init.d/nscd restart``` OF ```/etc/init.d/nscd restart```
 
 ## BIND server voor troubleshooting?
 
  Functie| Commando
 ----------| -------------------
 BIND server starten | ```service named start```
 BIND server stoppen | ```service named stop```
 BIND server restarten | ```service named restart```
 BIND server reloaden | ```service named reload```
 BIND server status | ```service named status```
