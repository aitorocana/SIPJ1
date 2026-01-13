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

- fer aquesta commanda per isntal·lar paquets de validacio de client

<img width="936" height="27" alt="image" src="https://github.com/user-attachments/assets/019b3872-4b7a-4320-9c5d-45813b6a25b6" />

Aqui treure una barra / i la i:

<img width="978" height="600" alt="image" src="https://github.com/user-attachments/assets/67f49a5e-7a09-4ffe-ab80-aaf93bd9e28d" />

Posar el teu domini:

<img width="978" height="600" alt="image" src="https://github.com/user-attachments/assets/d76867c4-24a8-4bc1-a660-cdc309ae4bbc" />

<img width="979" height="461" alt="image" src="https://github.com/user-attachments/assets/10237faa-1c0d-4279-b41f-a36cd1cdec0a" />

HO deixem per defecte

<img width="978" height="600" alt="image" src="https://github.com/user-attachments/assets/31e3bc6f-4274-4254-9891-caf19b091f8e" />

HO deixem per defecte

<img width="978" height="600" alt="image" src="https://github.com/user-attachments/assets/8938b9be-0c4e-4a35-bda9-d0c37157a3da" />

 cambiem a si

 <img width="978" height="600" alt="image" src="https://github.com/user-attachments/assets/cbaa1088-8f75-4662-b718-d160e90f4ebd" />

Posar contra i despres canviar aixó:

<img width="987" height="47" alt="image" src="https://github.com/user-attachments/assets/9d380a8d-df1c-481a-aacd-fdfa1b85d70a" />

Per si necesitem reconfigurar algo:

<img width="996" height="51" alt="image" src="https://github.com/user-attachments/assets/0966ee81-749e-4d31-8d44-9cecb0e79e01" />

Ara configurarem el primer fitxer:

<img width="988" height="35" alt="image" src="https://github.com/user-attachments/assets/b4ba539e-0c30-4842-804e-339047627891" />

- Agregar a les 4 ldap compat

<img width="845" height="435" alt="image" src="https://github.com/user-attachments/assets/9d91dac9-4a94-4ec3-945e-064e6166ba4a" />

- Ara un altre arxiu i anirem al final de tot i agreguem aquesta linia :

<img width="855" height="625" alt="image" src="https://github.com/user-attachments/assets/c6af230a-c1dc-4526-bbb7-7aa99602962e" />

- Ara amb la password i borrem use_authock als 3

<img width="855" height="625" alt="image" src="https://github.com/user-attachments/assets/9182cfda-812a-48b6-9705-9109633cf251" />

- Ara per ultim:

<img width="855" height="625" alt="image" src="https://github.com/user-attachments/assets/d343d2c0-9d0d-439a-bfe7-d8d06fc1c5a1" />

- tindrem que fer un grep de alu1 i veure si ens apareix

<img width="846" height="59" alt="image" src="https://github.com/user-attachments/assets/2f6b612e-f8fd-4089-8776-0a83156153a0" />

<img width="872" height="471" alt="image" src="https://github.com/user-attachments/assets/fc52ffb5-719e-4e77-8b1d-82207daf508e" />

<img width="984" height="110" alt="image" src="https://github.com/user-attachments/assets/9c0a37fc-70fa-4689-abca-38e99b5a643a" />

Ara reinicio i miro si puc accedir a usuari alu1 contra igual


