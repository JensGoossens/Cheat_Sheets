#DNS-server
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
