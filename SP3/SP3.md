# **Sprint 3: Gestió de Dominis i Accessos**


## **INSTAL·LACIÓ DOMINI LDAP I UNIR CLIENT AL DOMINI**

- Mini teoria: redactar sobre abres i dominis

Anar a fitxer, eines, network manager i crear NatNetwork. Després seguir els pasos següents, per al client i servidor d'ubuntu per a no tenir problemes amb la ip, establint  ala xarxa dels dos, la NatNetwork establerta. 

<img width="1221" height="853" alt="image" src="https://github.com/user-attachments/assets/82d03dd8-aa37-4390-8d70-e814318490c1" />

<img width="1221" height="853" alt="image" src="https://github.com/user-attachments/assets/d7e22481-9e16-4ca7-ab74-7cbaf3369288" />

Ara obrim el ubuntu anomenat "server". Probem ping a www.google.es i 8.8.8.8 i canviar cableat

fer nano /etc/hostname: es borra el que hi ha i fico ubuntuserver. tanco i guardo

<img width="840" height="449" alt="image" src="https://github.com/user-attachments/assets/868f581e-fb59-44e7-8e6f-45dcbb88ce0b" />

fer nano /etc/hosts i posar la nostra ip comprovada anteriorment amb un ip a al terminal i posar el hostname nou

<img width="840" height="449" alt="image" src="https://github.com/user-attachments/assets/3db941c4-a424-49f1-a68e-010671ca64b9" />

i fer un apt update despres

instal·lem 2 paquets: slapd i ldap-utils

<img width="840" height="449" alt="image" src="https://github.com/user-attachments/assets/0f2aded9-0378-4a7d-b9af-1b35774791ba" />
