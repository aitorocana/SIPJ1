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

<img width="984" height="110" alt="image" src="https://github.com/user-attachments/assets/9c0a37fc-70fa-4689-abca-38e99b5a643a" />

Ara reinicio i miro si puc accedir a usuari alu1 contra igual

<img width="711" height="223" alt="image" src="https://github.com/user-attachments/assets/25583eca-5207-4cac-b363-559ff0f7d6e3" />

---------------------------------------------------------

**EXERCICI**

- Primer que tot, ens baixem dades_github.ldif i fem un dpkg-reconfigure slapd al servidor per tal de deixar la base de dades buida i només amb el
domini i l’usuari admin creat. Després ho comprovarem amb un slapcat.

<img width="1090" height="574" alt="image" src="https://github.com/user-attachments/assets/5e378679-c11b-4e51-b683-d438a7c899a7" />

- Ara que tenim la base de dades buida, fem un gedit dades_github.ldif (nom del arxiu ldif) i canviar el domini vesper pel meu. En aquest cas, es gina. Per a fer-ho ràpid, selecciono el que vull canviar (dc) i faig un cerca i reemplaça canviant el domini per gina i ho desem.
  
<img width="1141" height="672" alt="image" src="https://github.com/user-attachments/assets/4909336b-7072-4ce5-aa55-2596cd6a10ed" />

- ldapadd---> per a posar el domini que hem canviat al gedit dades_github.ldif i al reconfigure:

<img width="1071" height="304" alt="image" src="https://github.com/user-attachments/assets/03e5d2d3-8957-417d-9b15-8628ae4c0682" />

- Comprovem que s'ha efectuat el canvi amb un slapcat.
  
<img width="1048" height="559" alt="image" src="https://github.com/user-attachments/assets/144cb4f7-5fe3-4bfb-934a-1a3339a236f2" />

- **Exercici 1:** Ara copiem un usuari i en crearem un de nou. Primer creem un nou arxiu.ldif i peguem el usuari de la base de dades que ja tenim. Després caviem nom i uid, per a que no sigui igual que la del usuari anterior, aixi creant-ne un de nou. Desem i tanquem i fem un altre ldapadd per agregar el nou canvi.

<img width="864" height="553" alt="image" src="https://github.com/user-attachments/assets/0608c3a8-dcb9-48c9-8431-278b1dac3ff8" />

- Comprovació amb slapcat:

<img width="760" height="435" alt="image" src="https://github.com/user-attachments/assets/b3575fab-cbdc-45c2-b0c5-b69e6e24283c" />

- **Exercici 2:** Ara crearem una uo. Basicament hem de fer els mateixos pasos, creació d'un arxiu buit, fer un gedit del arxiu posar la nova uo guardar i ldapadd.

<img width="760" height="435" alt="image" src="https://github.com/user-attachments/assets/1a148875-ff69-42ba-be63-47ec8e30de0e" />

<img width="755" height="123" alt="image" src="https://github.com/user-attachments/assets/743e63ab-ec26-4cd0-9d06-816588cba7d5" />

<img width="689" height="197" alt="image" src="https://github.com/user-attachments/assets/1f2a0ee8-be5d-487e-934b-7630469d4526" />

- **Exercici 3:** Ara mourem l'usuari Aitor que he creat a la nova uo. Utilitzem un dels arxius creats d'avans, borro lo anterior i fem aixó per a modificar el dn amb el que volem modificar.

<img width="689" height="197" alt="image" src="https://github.com/user-attachments/assets/b7e23c43-ede0-4177-92dd-1c2d780ba116" />

- Per últim fem un ldapmodify:

<img width="730" height="130" alt="image" src="https://github.com/user-attachments/assets/f532a5f1-c68b-4dd9-84a5-fa1506f9cc45" />

<img width="701" height="468" alt="image" src="https://github.com/user-attachments/assets/c368a598-973b-4df2-a075-1af49d96fa43" />

- **Exercici 4:** Fem un ldapsearch per veure quantes unitats organitzatives (uo) hi han. Ens surten 2, departaments i rrhh.

<img width="750" height="41" alt="image" src="https://github.com/user-attachments/assets/74fe0a4f-bd31-4630-a31b-dab799c5bcd7" />

<img width="340" height="151" alt="image" src="https://github.com/user-attachments/assets/9f305801-711b-4952-877e-02c432d8ea80" />

- **Exercici 5:** Ara el que farem es Afegir l’usuari que has creat dintre d’un dels grups del domini amb ldapmodify. Utilitzem un dels arxius creats d'avans, borro lo anterior i fem aixó per a afegir l'usuari creat dintre d'un dels grups de domini.

<img width="637" height="154" alt="image" src="https://github.com/user-attachments/assets/f1530f65-5916-4fc2-a2d4-4287f4f97021" />

<img width="725" height="106" alt="image" src="https://github.com/user-attachments/assets/31498d61-2ca6-4e42-9cad-2a0de4c0d0c3" />

<img width="690" height="493" alt="image" src="https://github.com/user-attachments/assets/c22d87c0-864f-41d2-99f2-a67416f6bdc5" />

- **Exercici 6:** D’un sol cop: Afegeix un nou atribut opcional a l’usuari sergi, modifica el cognom de l’usuari sergi al
valor Pallarés

<img width="658" height="507" alt="image" src="https://github.com/user-attachments/assets/c71a381e-6c30-4b0e-b160-4345fec067c2" />

- **Exercici 7:** Quants usuaris hi ha dintre de la uo rrhh? Quins són?

- Farem un ldapsearch en aquest cas. Podem observar que avans d'agregar el meu usuari a la rrhh, teniem els usuaris, sergi, enric i xavier. Per tnat, originalment n'hi havien 3

<img width="710" height="202" alt="image" src="https://github.com/user-attachments/assets/742cb82e-ee14-4d17-a1a4-3e97bca316ad" />

- **Exercici 8:** Esborra el gidNumber del grup informàtica

No es podria esborrar el gidnumber del grup d'informàtica degut a que l'atribut gidNumber es obligatori per a que funcioni el grup

- **Exercici 9:** Quantes uos hi ha al domini vesper.cat? (gina en aquest cas)

<img width="921" height="476" alt="image" src="https://github.com/user-attachments/assets/16748ee7-0acc-4c70-a506-bb1a7dc979e3" />

- **Exercici 10:**  Modifica el cn de Xavier per Francesc Xavier

<img width="693" height="454" alt="image" src="https://github.com/user-attachments/assets/b07218c2-5753-428e-8383-5be797a30fb0" />

<img width="702" height="135" alt="image" src="https://github.com/user-attachments/assets/2eb80a6b-b7e7-44c7-b9da-32419757fa03" />

- comprovacio:

<img width="702" height="135" alt="image" src="https://github.com/user-attachments/assets/bebe18ba-07e3-4764-89c0-fc8aa06673c1" />

- **Exercici 11:**  Esborra la uo nòmines

- Faig la comanda ldapdelete, amb la uo que vull eliminar:

<img width="689" height="56" alt="image" src="https://github.com/user-attachments/assets/578fbf36-75a2-441e-8e13-cde9811e7467" />

<img width="749" height="291" alt="image" src="https://github.com/user-attachments/assets/024e083e-3d95-41ef-bbcc-fa9164c7c370" />

- **Exercici 12:**  Mostra els usuaris que tinguin com a grup principal el grup administració

- Fem un slapcat i busquem el grup principal d'administració, veiem que té un gidnumber asociat, per tant haurem de filtrar amb aquest gidnumber per saber quins usuaris el tenen

<img width="575" height="101" alt="image" src="https://github.com/user-attachments/assets/85f3f275-e352-41d2-9f2b-3ad158f6caa7" />

<img width="694" height="741" alt="image" src="https://github.com/user-attachments/assets/6bc0222f-94f0-4a1a-9430-2de88b4ca4eb" />

- **Exercici 13:**  Quin usuari té el uidNumber 1003?

- Principalment, no hi havia cap usuari amb uidNumber 1003, però com vaig crear un usuari amb aquest uidNumber per a un excercici anterior, hem mostra aquest:

<img width="696" height="579" alt="image" src="https://github.com/user-attachments/assets/79db1787-fdf2-440a-b2c9-f34f5c5ada9c" />

- **Exercici 14:**  Mostra quins són els usuaris on el seu cognom comenci per R i el seu uidNumber sigui més gran que
1003

<img width="696" height="579" alt="image" src="https://github.com/user-attachments/assets/537e12f1-25a8-4592-8067-325bcd72beaf" />

- **Exercici 14:**  Mostra quins usuaris formen part del grup informàtica o aquells usuaris que tinguis de cognom
Pallarés

- Mirem els usuaris del grup informatica

<img width="702" height="418" alt="image" src="https://github.com/user-attachments/assets/def44674-1310-4348-a035-039ee142b5ef" />

- Mirem els usuaris de cognom pallares

<img width="678" height="605" alt="image" src="https://github.com/user-attachments/assets/3366118b-b0d5-4e05-83bd-bd567c297d29" />




------------------------------------------------------------------

Teoria servidor samba i fns: 

Els SAMBA serveixen per a compartir arxius, recursos... a mes a mes SAMBA us permet compartir impresores i fer l'autenticació a través de un ldap (no es prescindible).

FNS, funciona mes a nivell de host o de ip, pot accedir a aquest recurs el ordinador que té aquesta ip, però també serveix per a compartir arxius.

**1. PART SERVIDOR**

- **instal·lem SAMBA al ubuntu server que vam fer**:

<img width="639" height="372" alt="image" src="https://github.com/user-attachments/assets/98aeeec8-d992-4ab5-8ccd-e8797e372385" />

- Anem a l'arrel, creem carpeta i fitxer, donem permisos

<img width="602" height="195" alt="image" src="https://github.com/user-attachments/assets/8b03a994-4e4a-46c3-b72f-e8ce60e6e884" />

- Creem usuaris i un grup. pero no volem usuaris que puguin entrar per interficie gràfica sino per SAMBA.

<img width="636" height="383" alt="image" src="https://github.com/user-attachments/assets/c79fb777-3c69-4ecd-a21b-3b5c506d76eb" />

-  Creem el grup i despres assignem a groc i roig dintre del grup colors creat.

<img width="636" height="383" alt="image" src="https://github.com/user-attachments/assets/fac491cf-dfd8-4e9d-bf93-db5232f5d633" />

- Entrem al arxiu de configuracio de samba i anem baix de tot, i definim qui pot accedir, qui pot llegir, escriure, etc...

<img width="643" height="409" alt="image" src="https://github.com/user-attachments/assets/451bceeb-6e78-469a-b272-6d37257aa500" />

- Per a comprovar hem de reiniciar systemctl restart i comprovar-ho amb l'estatus

<img width="510" height="42" alt="image" src="https://github.com/user-attachments/assets/01eeb8bb-8527-4b04-b71d-17cd68243e30" />

<img width="647" height="417" alt="image" src="https://github.com/user-attachments/assets/db0b4292-d687-4ace-b94e-36e827161876" />

**2. PART CLIENT**

- instal·lem smbclient

<img width="633" height="40" alt="image" src="https://github.com/user-attachments/assets/f74059e1-ee32-459b-affb-c223f0919274" />

- fer un ip a i fer un ping al server

- Nem a fitxer i altres ubicacions ----> fiquem la ip del server i l'arrel del fitxer entrem ens connectem i creem un fitxer per veure que tenim permisos
  
<img width="873" height="654" alt="image" src="https://github.com/user-attachments/assets/f80f9e29-f6e3-4659-acb8-f4c0d7c3929f" />

- Ara provem entrant igual pero posant usuari registrat els colors que haviem creat per veure si funciona 

<img width="873" height="654" alt="image" src="https://github.com/user-attachments/assets/276b8074-3204-4dbd-a368-58a52c82a2a0" />

- En l'usuari roig, sera l'unic que no ens deixarà ni accedir, amb els altres no es sortira aquesta pestanya:

<img width="873" height="654" alt="image" src="https://github.com/user-attachments/assets/7ef24095-46db-4936-bb7d-8758945597d4" />


-------------------------------------

EXERCICI ES ACABAR LO DEL LDAP DEL ATRE DIA I DONAR PERMISOS ALS USUARIS ESTOS QUE ASTIC FENT AL EXERCICI PER A QUE A ALTRE UBICACIONS FICANT EL PING AL SERVER PUGUESIM ENTRAR AMB ELS USUARIS AMB ELS PERMISOS ADEQUATS I TAL A L'AXIU SAMBA


---------------------------------------


- NFS: serveix per a compartir carpetes dintre d'una xarxa interna pero la autentificació es a nivell de hosts. FNS, funciona mes a nivell de host o de ip, pot accedir a aquest recurs el ordinador que té aquesta ip, però també serveix per a compartir arxius.

**1. PART SERVIDOR**

**Apt update sempre avans que res**

- instal·lem nfs-kernel-server al servidor:

<img width="719" height="308" alt="image" src="https://github.com/user-attachments/assets/d43c9f91-f3a8-44d4-99f2-c25fb43b4566" />

- comprovem que estigui actiu:

<img width="729" height="189" alt="image" src="https://github.com/user-attachments/assets/b9299f4c-0f5a-4a1a-9312-f33a15dcd0fa" />

- Des de l'arrel creem un nou arxiu

<img width="726" height="124" alt="image" src="https://github.com/user-attachments/assets/3b868eba-bbd1-45c5-adce-00e080617c30" />

- entrem a l'arxiu nano /etc/exports i creem permisos de la carpeta (lo asterisc diu que serveix per a que tinguin permis tots els ordenadors (*)):

<img width="690" height="472" alt="image" src="https://github.com/user-attachments/assets/df299726-5681-4d8c-b0f9-fc28e2e95afc" />

- reiniciem el nfs-kernel-server
  
<img width="603" height="105" alt="image" src="https://github.com/user-attachments/assets/d78489ed-90b2-4984-a539-7d1a505e88d6" />

- fem un ip a i mirem la nostra ip del server

**2. PART CLIENT**

**Apt update sempre avans que res**

- instal·lem uns paquets ---> nfs-common rpcbind :

<img width="719" height="330" alt="image" src="https://github.com/user-attachments/assets/291ba082-4d81-4d61-bcc5-411dd19130d8" />

- la carpeta del server que tenim, es monti automaticament a la que creem del client:

<img width="699" height="140" alt="image" src="https://github.com/user-attachments/assets/480ab50b-e61e-4297-9fe8-5ebe8f8579a5" />

- entrem al fstab ---> nano /etc/fstab per al fer el muntatge

<img width="1088" height="346" alt="image" src="https://github.com/user-attachments/assets/99201a2d-f45a-4f52-8b12-639d718e172f" />

i fem un reboot al client


3. **COMPROVAVIONS**

- Ara al **server** a la carpeta provesnfs creem un arxiu:
  
<img width="684" height="134" alt="image" src="https://github.com/user-attachments/assets/4cd55b3c-4102-426c-816f-d2864a103c47" />

- entrem al **client** a la carpeta divendres i fem un ls i ens surt l'arxiu creat al server. Per últim crearem l'arxiu adeu, per veure si ho capta el **servidor** desde la carpeta provesnfs

<img width="737" height="168" alt="image" src="https://github.com/user-attachments/assets/97159405-d0a3-4c62-a6cd-15990371e7fc" />

- Comprovació del **servidor** que ens surt l'arxiu adeu:

<img width="737" height="95" alt="image" src="https://github.com/user-attachments/assets/76e9d7cc-d00c-4385-9b32-df1adb603b1d" />

- Podem veure que la carpeta provesnfs del servidor apunta al client i al revés.

--------------

mini exercici: agafem un windows dintre de la mateixa XARXA NAT i conectarme per nfs a panel de control a servicios NFS i fer un check a la casella, reiniciar, i desde xarxa a ver si es veu el client server nfs

----------

- Creem un ariu perfils li donem permisos i fem un gedit /etc/fstab

<img width="759" height="117" alt="image" src="https://github.com/user-attachments/assets/1c94d12f-f96e-4747-94d9-c9200cbc9898" />

- copiem la ultima linia del gedit la peguem baix seva i canviem l'arrel de l'arxiu divendres al nou creat perfils.

<img width="1100" height="319" alt="image" src="https://github.com/user-attachments/assets/79e9de6f-c614-4d6d-b666-0dfe4f5f0c16" />

**Part server**

- creem el mateix arxiu que al client i li donem permisos i comprovem

<img width="708" height="206" alt="image" src="https://github.com/user-attachments/assets/4aa7018b-eab5-4451-a190-2bc8aa240be4" />

- fem un gedit /etc/exports i copiem i peguem l'ultima linia i fiquem l'arrel del arxiu

<img width="702" height="333" alt="image" src="https://github.com/user-attachments/assets/6590b1d6-339c-40c1-bc6f-9368f92363d8" />

- fem un restart del nfs-kernel-server

<img width="758" height="46" alt="image" src="https://github.com/user-attachments/assets/4a70f91c-4d02-4bd8-9bfb-2d14a18043a5" />

- fem un slapcat dintre de baixades per veure el ldap que tenim, i ens quedem amb un grup de posixgroups i amb el domini, informatica i gina i cat i el numero gid 1001

- Modifiquem el usu.ldif per a que sigui el home directory perfils i trec la uo: users

<img width="724" height="467" alt="image" src="https://github.com/user-attachments/assets/8535eb15-e2fb-4429-ba6a-622f40b66016" />

**part client**

- anem al client i entrem amb l'usuari alu3 alu3 i hem pogut entrar correctament.

<img width="941" height="632" alt="image" src="https://github.com/user-attachments/assets/dd80ca35-eb02-4c25-99c2-0853e2bf60bc" />








