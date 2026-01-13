# **Sprint 3: Gestió de Dominis i Accessos**


## **INSTAL·LACIÓ DOMINI LDAP I UNIR CLIENT AL DOMINI**

- Mini teoria: redactar sobre abres i dominis

Anar a fitxer, eines, network manager i crear NatNetwork. Després seguir els pasos següents, per al client i servidor d'ubuntu per a no tenir problemes amb la ip, establint  ala xarxa dels dos, la NatNetwork establerta. 

<img width="1221" height="853" alt="image" src="https://github.com/user-attachments/assets/82d03dd8-aa37-4390-8d70-e814318490c1" />

<img width="1221" height="853" alt="image" src="https://github.com/user-attachments/assets/d7e22481-9e16-4ca7-ab74-7cbaf3369288" />

Ara obrim el ubuntu anomenat "server". Probem ping a www.google.es i 8.8.8.8 i canviar cableat

<img width="801" height="524" alt="image" src="https://github.com/user-attachments/assets/7f6f3752-936d-4aaa-bc1d-1e8d058e618c" />

fer nano /etc/hostname: es borra el que hi ha i fico ubuntuserver. tanco i guardo

<img width="840" height="449" alt="image" src="https://github.com/user-attachments/assets/868f581e-fb59-44e7-8e6f-45dcbb88ce0b" />

fer nano /etc/hosts i posar la nostra ip comprovada anteriorment amb un ip a al terminal i posar el hostname nou

<img width="840" height="449" alt="image" src="https://github.com/user-attachments/assets/3db941c4-a424-49f1-a68e-010671ca64b9" />

i fer un apt update despres

instal·lem 2 paquets: slapd i ldap-utils

<img width="840" height="449" alt="image" src="https://github.com/user-attachments/assets/0f2aded9-0378-4a7d-b9af-1b35774791ba" />

<img width="840" height="449" alt="image" src="https://github.com/user-attachments/assets/83c2ca9c-85b6-4719-944e-7baee6319532" />

<img width="840" height="449" alt="image" src="https://github.com/user-attachments/assets/e0a4c0a0-6440-4579-87b7-c0958ee987e4" />

<img width="731" height="297" alt="image" src="https://github.com/user-attachments/assets/e35b5ae9-489f-4299-bafd-c72fbe3936a9" />

Descarreguem arxius.zip del moodle i fer:

<img width="849" height="698" alt="image" src="https://github.com/user-attachments/assets/0c98665f-ee07-42a8-998a-f82f9b92ec8a" />

<img width="573" height="461" alt="image" src="https://github.com/user-attachments/assets/da6f9a56-4b51-4d26-a5ce-a78e8fd75941" />

<img width="573" height="461" alt="image" src="https://github.com/user-attachments/assets/0dcb50e7-b128-4d67-9cb3-38d69e402705" />

- fer ---> nano uo.ldif i comentar que es aixo:

<img width="728" height="173" alt="image" src="https://github.com/user-attachments/assets/33e7a549-a0d2-4547-a823-ada1db8ff27c" />

- fer nano de grup.ldif

<img width="728" height="173" alt="image" src="https://github.com/user-attachments/assets/f3112a1b-a151-44c2-9d83-dd1026cc0a34" />

-fer nano de usu.ldif (usuari):

<img width="741" height="407" alt="image" src="https://github.com/user-attachments/assets/39ea7129-e446-4779-91fd-dd7f875fb88e" />

- Ara carreguem els tres amb ldapadd -c -x -D

<img width="932" height="204" alt="image" src="https://github.com/user-attachments/assets/1cb01108-8e04-4809-bedd-3f0c5613777f" />

<img width="1315" height="798" alt="image" src="https://github.com/user-attachments/assets/7126ebce-ccb4-469e-94b5-c23773b965d0" />

- Ara obrim el **client** ubuntu i fem un ping al server

<img width="941" height="435" alt="image" src="https://github.com/user-attachments/assets/8802462a-587f-4f7b-bbb9-3fae5e67086b" />




