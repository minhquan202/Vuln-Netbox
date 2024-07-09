**Description:**

Store XSS on the list api:

-core/config-revisions/add/ (Param: BANNER_MAINTENANCE or BANNER_LOGIN)
-/dcim/interfaces/{id}/edit/ or /dcim/interfaces/add (Param: NAME)
of NetBox version v4.0.6 ([https://github.com/netbox-community/netbox](https://github.com/netbox-community/netbox)) allow remote attackers to hijack user's cookie 

**Proof of Concept:**

1. Add or edit the above API list with malicious script tags at Param malicious.
2. with api core/config-revisions/add/ after adding, access the newly created config -> click edit -> Store XSS execute
3. With api /dcim/interfaces/{id}/edit/ or /dcim/interfaces/add, after creating or editing the name interface, assign it as Child Interfaces to another parent interface.
4. move to the parent interface. Deleting that interface immediately cannot be deleted because it is tied to child interfaces. Immediately Store XSS is executed
**Impact:**

Hijack user's cookies.

With core/config-revisions/add/
![image](https://github.com/minhquan202/Vuln-Netbox/assets/89106168/66887463-e72f-4e6d-affe-f32d8796682b)
![image](https://github.com/minhquan202/Vuln-Netbox/assets/89106168/6dfba611-b99c-4070-8fae-5fdd1986aaea)
![image](https://github.com/minhquan202/Vuln-Netbox/assets/89106168/0379ea39-e84f-462d-968c-dea24c786348)
![image](https://github.com/minhquan202/Vuln-Netbox/assets/89106168/b2f36926-a79d-40c4-b8c6-0eb7129f3ecd)

With /dcim/interfaces/{id}/edit/ or /dcim/interfaces/add
![image](https://github.com/minhquan202/Vuln-Netbox/assets/89106168/6799a92b-357a-4e22-89d1-0d32efcf3afe)
![image](https://github.com/minhquan202/Vuln-Netbox/assets/89106168/b30c4e4f-c081-407d-860f-be0a3f96deec)
![image](https://github.com/minhquan202/Vuln-Netbox/assets/89106168/675985f0-771b-4b86-b741-fc48bedeb942)
![image](https://github.com/minhquan202/Vuln-Netbox/assets/89106168/aa7ff0c8-6c57-4178-8c85-0f53acce817b)

