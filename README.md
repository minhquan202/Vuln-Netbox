```
Description:
Store XSS on the list api: 
/dcim/power-ports/add/
/dcim/power-ports/{id}/edit/ 
/dcim/console-server-ports/add/
/dcim/console-server-ports/{id}/edit/
/dcim/interfaces/add/ 
/dcim/interfaces/{id}/edit/ 
/dcim/rear-ports/{id}/edit/ 
/dcim/rear-ports/add/
/dcim/front-ports/{id}/edit/
/dcim/front-ports/add/
/dcim/power-outlets/{id}/edit/
/dcim/power-outlets/add
/dcim/console-ports/add
/dcim/console-ports/{id}/edit/
/dcim/power-feeds/add
/dcim/power-feeds/{id}/edit/
/circuits/circuits/{id}/edit/
/circuits/circuits/add
of NetBox version 4.0.3 (https://github.com/netbox-community/netbox) allow remote attackers hijack user's cookies attack via param Name except for api a, param is Circuit ID.
Proof of Concept:
1, Add or edit the above api list with malicious script tags at Param malicious
2, Go to api connections > cables to connect malicious device components together
3, After connecting successfully, when accessing api Connection > Cables again, the XSS Vulnerability immediately appeared
Impact:
hijack user's cookies
```
![image](https://github.com/minhquan202/Vuln-Netbox/assets/89106168/36f5d549-87bd-4f8f-91ea-140078e5a3dd)
![image](https://github.com/minhquan202/Vuln-Netbox/assets/89106168/25ec0136-4e4e-4c2e-84b8-9367c27aac2c)
![image](https://github.com/minhquan202/Vuln-Netbox/assets/89106168/07c12038-c91c-45a5-b52a-6163d374d2ce)
