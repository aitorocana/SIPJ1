---
layout: default
title: "SP1 Avaluació, Instal·lació i Configuració de Xarxes i Sistemes Operatius"
---

# **Virtualització i instal·lació del SO Ubuntu**
## **Fase 1. Virtualització**

**1.** Per a la vitualització, primer busquem els requisits mínims que demana UBuntu a la seva documentació oficial, per tal de saber més o menys el que hem de posar:

<img width="922" height="555" alt="image" src="https://github.com/user-attachments/assets/9ebd2d0b-a558-4122-b85d-a03c8ea73f14" />

**2.** Per tant, com podem veure, ens demana segons la documentació, una RAM mínima d'uns 3GB i un almacenament mínim de 25GB per a que funcioni minimament.
Nosaltres hem escollit, tal i com podem veure en la següent captura, una RAM de 4GB i hem assignat un almacenament de 80GB.

<img width="1172" height="859" alt="image" src="https://github.com/user-attachments/assets/7fad345c-dd0d-49ef-aca7-9acbce5a4c42" />

**3.** En la següent imatge, començem a escollir la carpeta de destinatari de la nova màquina virtual, escollint el nom que es visualitzarà com a nova màquina virtual amb el seu sistema operatiu escollit. Però encara no triem la ISO. Ho farem després.

<img width="871" height="473" alt="image" src="https://github.com/user-attachments/assets/9d2321fd-699a-4430-bed2-766afc7cb368" />

**4.** En aquesta part, el que fem es triar la destinació de memòria que li volem donar per a un funcionament correcte de la nostra màquina virtual, juntament
amb quants de nuclis volem posar. Sempre seguint els requisits mínims que ens demana la documentació oficlal.

<img width="879" height="476" alt="image" src="https://github.com/user-attachments/assets/c8d9af39-81cf-4ed1-8c75-a5ce6abff082" />
<img width="879" height="476" alt="image" src="https://github.com/user-attachments/assets/3b8de964-8e64-418e-b752-0d86aad15398" />

**5.** Aqui, dintre de paràmetres del client, a emmagatzematge escollim la ISO que volem, que en aquest cas serà l'ubuntu desde el fitxer on el teniem guardat

<img width="873" height="580" alt="image" src="https://github.com/user-attachments/assets/34bb7107-b7bb-4573-80d1-669dad129bf8" />


 ## **Fase 2. Instal·lació**

**1.** En el moment de la instal·lació, ens demanarà l'idioma que volem escollir, després el tipus d'instal·lació que volem i el que ens interessa es l'opció de crear particions:

<img width="908" height="662" alt="image" src="https://github.com/user-attachments/assets/b2995272-1591-44da-a0cc-5d754c4e74d1" />

**2.** Aquí procedim a dividir el disc sorbe les 80GB que hem escollit en el moment de la virtualització de la màquina virtual. Però com pròximament instal·larem amb aquestes 80GB el windows,
deixem 40GB a banda, que les destinarem per a l'instal·lació del Windows i les altres 40GB per a l'Ubuntu.

<img width="1282" height="865" alt="image" src="https://github.com/user-attachments/assets/5263f550-3d31-45dc-81b7-0f030162bf60" />

**3.** El cas es que hem de pensar que sol tenim 40GB disponibles per a l'Ubuntu i per a repartir aquests per a la repartició que necessita Ubuntu per a la instal·lació. 
Primer dividirem 25 GB, per a l'arrel que es on van instal·lats els programes i el sistema.

<img width="862" height="649" alt="image" src="https://github.com/user-attachments/assets/cd540697-7714-4385-b25c-50a9d1bec1ed" />

**4.** Ara destinarem 13GB per al /home, que es on van guardats els teus fitxers.

<img width="862" height="649" alt="image" src="https://github.com/user-attachments/assets/97b35073-988e-4867-9d5b-b3936b8d86f1" />

**5.** Destinem 2GB per al /swap, que bàsicament es la memòria d'intercanvi.

<img width="862" height="649" alt="image" src="https://github.com/user-attachments/assets/713eb178-ab58-414b-a295-1555ee132615" />

**6.** Agreguem aqui 1GB per a la EFI per a guardar el sistema d'arrancada.

<img width="862" height="649" alt="image" src="https://github.com/user-attachments/assets/e9925874-f2b4-4700-9dff-8cdc2dd35f9b" />

**7.** Aqui fem l'última partició d'1GB per al BIOS boot.

<img width="843" height="640" alt="image" src="https://github.com/user-attachments/assets/d3466d99-f3fe-4ba5-a556-e1fb692c969b" />

**8.** Al haver creat totes les particions, li donem a instal·lar i escollirem el nostre usuari que personalitzarem escollint el nom que volem que sorti.

<img width="843" height="640" alt="image" src="https://github.com/user-attachments/assets/2193e1c0-98d8-4985-9e3f-27fbbdec916d" />

## **Fase 3. Llicenciament**

**1.** Per a comprobar lles llicències d'Ubuntu que tenim instal·lades, les mirarem mitjançant la commanda de la fotografia següent. La captura ens mostra les llicències que utilitza Ubuntu, entre elles destacariem la de GPL. Aquesta es una llicència que permet compartir, usar i modificar el software, fent-lo d'ús lliure. Però, aplicant aquesta llicència dona una protecció dels drets dels usuaris que vulguin utiltizar aquesta distro.
Tambè podem trobar destacades la GFDL i la LGPL que bàsicament també permeten la lliure distribució basant-se amb la llicència GPL que es una mica més restrictiva.

<img width="589" height="136" alt="image" src="https://github.com/user-attachments/assets/ff469463-9d21-4ec5-bf6e-1bc164986dac" />

## **Fase 4. Instal·lacions duals i gestors d'arrancada**

**1.** Aqui seleccionem el disc òptic per seleccionar l'ordre d'arrancada, sempre posant la memòria que ens demana mínima per a executar-ho. Després a "**Extended Features**", hem de posar l'opció activa EFI per a que s'executi Ubuntu bé després.

<img width="892" height="585" alt="image" src="https://github.com/user-attachments/assets/bf57659d-ba70-44be-a29d-b3365a813866" />

**2.** Seleccionem la ISO de Windows que vam descarregar per determinar la partició que volem per a windows de la principal que vam fer anteriorment de 40GB

<img width="892" height="585" alt="image" src="https://github.com/user-attachments/assets/6a20b696-bcb3-4277-85e2-ce2cb5d40518" />

**3.** Aquí escollirem la opció avançada d'instal·lació de Windows per a elegir la partició i creem la de 40GB que serà la meitat que vam destinar per a aquesta partició.

<img width="704" height="508" alt="image" src="https://github.com/user-attachments/assets/3eeddcd2-2d14-48d4-af4a-096f28a84dfa" />

**4.** Després al acabar d'instalar-ho. Tancarem, anirem a paràmetres del client que hem creat del virtualbox d'ubuntu, i escollirem la iso del grub descarregada per a poder reparar el grub posteriorment.

<img width="875" height="556" alt="image" src="https://github.com/user-attachments/assets/9842beaf-981f-4fd4-9166-88c5a6d5d3dc" />

**5.** Aquí executarem el client i li donarem varies vegades a la tecla "**ESC**" per a obrir la terminal de BIOS. Escollirem el BOOT Manager Menu i escollirem la següent ISO que es la del grub.

<img width="665" height="565" alt="image" src="https://github.com/user-attachments/assets/e0e99135-15c9-4c2c-8ac1-60e2895e0b59" />

**6** Després ens sortira aquest menú on escollirem l'opció "**Detect and show methods**".

<img width="665" height="565" alt="image" src="https://github.com/user-attachments/assets/94446828-6c6e-49ab-a731-89e7f2a49f8b" />

**7.** Aquí escollirem el nostre línux que vam instal·lar per a procedir a reparar el grub.

<img width="665" height="565" alt="image" src="https://github.com/user-attachments/assets/d5af747c-93ec-4c09-87ba-437813bc3d71" />

**8.** En el moment d'entrar a ubuntu, obrim la terminal. Escriurem la commanda " **sudo su**". Instal·larem  el paquet amb "**apt install efibootmgr**", després instal·lem "**apt install grub-efi**", després farem "**apt install --reinstall grub-pc**", Després d'haver ja creat el grub després posarem la commanda "**mkdir /boot/efi**". Posteriorment reinstal·lem el Grub a la unitat " **grub-install /dev/sda**" i "**grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=ubuntu**"
Aqui ara com veurem , mitjançant la commanda "**nano /etc/default/grub**", hem de fer varies coses per a acabar de restaurar el grub. Primer hem de comentar amb "**#**" el "**GRUB_TIMEOUT_STYLE=hidden**" i el "**GRUB_TIMEOUT=0**". Per últim descomentem treien "**#**" o si no ens surt escriure el text: "**GRUB_DISABLE_OS_PROBER=false**". Tanquem i guardem.

<img width="806" height="426" alt="image" src="https://github.com/user-attachments/assets/ed1e9d23-4ee3-4205-9439-c7ea08ae8406" />

**9.** Aquí posarem la commanda "**update -grub**" per a tenir actualitzada la configuració que hem fet i poder veure que hem restaurat el grub. Però encara no hem acabat.

<img width="751" height="491" alt="image" src="https://github.com/user-attachments/assets/d30937d3-6c1e-47b3-962d-d26b0948e5b9" />

**10** Aquí obrim terminal una altra vegada per a veure la posició d'arranc del grub que tenim configurada. Però aquesta la tenim que canviar per a posar per a que al iniciar el virtualbox ens sorti el gestor d'arranc del grub i així poder escollir el SO que volem iniciar, si Ubuntu o WIndows.

<img width="751" height="491" alt="image" src="https://github.com/user-attachments/assets/c5d15e7d-44f1-479e-9597-013ccc5edace" />

**11.** Per a que surti la posició de l'arranc que volem i compilar-la per a que ens surti al grub, hem de canviar la posició dintre del "**BootOrder**", fent que ubuntu sigui primer en el procés d'arranc del grub, perque sinó sempre començara iniciant windows primer. Després en la segona posició posem la iso del client del virtualbox i després posem les altres restants, sempre posant-les totes per a que no ens doni ningun tipus d'error. Després ho guardarem i ho tancarem.

<img width="595" height="216" alt="image" src="https://github.com/user-attachments/assets/9eef9635-a341-4f1e-a9a5-380a76584ec8" />

**12.** Sí ho hem fet tot bé, al iniciar el client de virtual box ens tindria que sortir tal com la següent imatge.

<img width="823" height="518" alt="image" src="https://github.com/user-attachments/assets/aa413ced-c20b-4bd9-ad78-0fe2188e6df5" />


 ## **Fase 5. Particions i punts de restauració instantània**
 
 **1.** Primer anar a paràmetres del client creat d'Ubuntu, anar a emmagatzematge i crear un nou disc a la part dreta del controlador sata.
 
<img width="865" height="539" alt="image" src="https://github.com/user-attachments/assets/aa886bdc-c974-40b9-a79b-0fe58673699f" />

 **2.** A Paràmetres canviem la xarxa a adaptador pont

<img width="865" height="539" alt="image" src="https://github.com/user-attachments/assets/e423645c-da76-4304-b974-fe682e712984" />

 **3.** Ara obrim terminal,posem sudo su. Ara entrarem al disc que hem creat sbd per a crear la partició.

<img width="865" height="539" alt="image" src="https://github.com/user-attachments/assets/7e3313cd-1235-4047-adb6-6ddf38243aae" />

**4.** Aquí crearem ja la partició.

<img width="833" height="585" alt="image" src="https://github.com/user-attachments/assets/43e77387-4b42-40a3-bb58-fe8bd3c1b397" />

**5.** Veurem la partició creada de la següent forma:

<img width="717" height="220" alt="image" src="https://github.com/user-attachments/assets/af65e2af-79b9-4b60-bc3a-e995fdd2b858" />

**6.** Aquí el que farem serà el formateig de la partició mitjançant la commanda ----> mkfs.ext4. AIxò crearà un nou sistema o estructura de fitxers.

<img width="717" height="416" alt="image" src="https://github.com/user-attachments/assets/7cf85d00-ae75-438c-a0cc-65cf8cfbdc79" />

**7.** En aquest pas instal·larem timeshift que ens servirà per a la recuperació d'arxius esborrats.

<img width="742" height="461" alt="image" src="https://github.com/user-attachments/assets/c74c079d-0cc9-4542-ae7e-fb7fbbaf8b1e" />

**8.** Amb la linia de commandes següents, crearem una carpeta de prova per a comprovar el funcionament del timeshift.

<img width="577" height="253" alt="image" src="https://github.com/user-attachments/assets/a3238b6f-6a4e-4c46-9592-be7fa7c4817d" />

**9.** Aquí començarem amb la configuració d'aquest programa.

<img width="623" height="684" alt="image" src="https://github.com/user-attachments/assets/da64d79f-e5fc-4db8-9c8f-a31d6fad8840" />

**10.** Tindrem que escollir la ubicació de la partició que hem creat i que volem utiltizar.

<img width="623" height="684" alt="image" src="https://github.com/user-attachments/assets/fa2d5728-48f7-4d12-b082-bfef8c9604ff" />

**11.** Seleccionarem el nivell d'arranc per a especificar els intervals de la creació de les instantànies.

<img width="623" height="684" alt="image" src="https://github.com/user-attachments/assets/1142b780-0529-48ec-a961-7d92ffad69a9" />

**12.** Escollirem els arxius que volem seleccionar per a incloure o no en el moment de la recuperació. Aquí triarem tots els arxius de l'arrel del sdb1.

<img width="821" height="684" alt="image" src="https://github.com/user-attachments/assets/faab9a72-3f29-489b-926b-3c8179cde4ea" />

**13.** Aquí triarem quins directoris volem incloure o excloure.

<img width="777" height="694" alt="image" src="https://github.com/user-attachments/assets/81163cca-f731-4dbf-bee5-75c1ff45b85b" />

<img width="766" height="651" alt="image" src="https://github.com/user-attachments/assets/745a95ed-6244-47ff-b41a-c88adcfc2f31" />

**14.** Ara tornarem a comprovar si a la carpeta on haviem creat l'arxiu de prova ha sigut eliminat o no mirant si existeix. Efectivament tal i com veiem a la següent captura, l'hem eliminat correctament.

<img width="766" height="543" alt="image" src="https://github.com/user-attachments/assets/8c32f363-dd21-4463-919b-22fc719257f5" />

**15.** Ara tornarem al TImeshift, i utilitzarem l'opció de restauració i restaurarem els documents eliminats

<img width="595" height="595" alt="image" src="https://github.com/user-attachments/assets/c4fbc6e2-4927-4f30-a7ca-059d51e6532b" />

**16.** Tornarem a comprovar, mitjançant aquesta linia de commandes, si dintre de Documents (que es on haviem creat l'arxiu de prova al principi) apareix de nou l'arxiu eliminat. Finalment, podem comprovar que ens ha funcionat la restauració ja que torna a aparèixer.

<img width="716" height="240" alt="image" src="https://github.com/user-attachments/assets/b3385b5a-ca0f-47ee-9614-386f2bebfd1b" />

 ## **Fase 6. Configuració bàsica de la xarxa**

 **1.** Primer comprovem la ip amb la commanda per terminal ubuntu ----> ip a. Després procedirem a canviar la nostra ip.
 <img width="1182" height="784" alt="image" src="https://github.com/user-attachments/assets/8728199b-49df-4188-9ae4-ca66b2cac6f2" />
  
 <img width="715" height="490" alt="image" src="https://github.com/user-attachments/assets/a101ce67-26be-4d13-be15-57919fcfab7c" />

 **2.** Aquí amb el ping i un link d'internet veurem si s'ha aplicat bé la ip nova.

 <img width="726" height="276" alt="image" src="https://github.com/user-attachments/assets/52a3cdcd-08d6-4a35-84a1-292b40afd5e7" />

 **3.** Aquí amb el ping i la DNS veurem si s'ha aplicat bé la DNS nova.
  
 <img width="725" height="226" alt="image" src="https://github.com/user-attachments/assets/ba2345d2-1fda-4234-8b44-0504bc0af0dc" />

 **4.** Deixem la configuració de red com avans amb el DHCP automàtic.

 <img width="591" height="473" alt="image" src="https://github.com/user-attachments/assets/027b93ab-5cfd-4c4a-9844-c0032b71002b" />

 **5.** Fem el mateix pero mitjançant terminal.

 <img width="782" height="501" alt="image" src="https://github.com/user-attachments/assets/54c49660-8e59-4118-bf35-eaa6cce70d81" />

 <img width="781" height="335" alt="image" src="https://github.com/user-attachments/assets/314a9e06-84e6-4d5d-abb7-4f8c90557cfc" />

 <img width="788" height="467" alt="image" src="https://github.com/user-attachments/assets/2969a426-ae15-4cbc-abd1-b42c4b158be8" />
  


 ## **Fase 7. Comandes generals i instal·lació de paquets**

 - ### **Instal·lació amb el apt-get o apt**

 **1.** Primer insta·laré amb el "apt-get install (paquet)" o "apt install (paquet)" el paquet "dia". Però avans sempre assegurar-se de posar-te com a super usuari per a tenir tots el persmissos per poder instal·lar-ho.`La commanda seria -----> sudo su.
 
 <img width="1180" height="723" alt="image" src="https://github.com/user-attachments/assets/b61b711e-283f-449a-b2e2-33c8e2015c1c" />
 
 **2.** Ara comprobem que efectivament ho hem instal·lat correctament visualitzant-ho al menu d'aplicacions i veurem com s'executa correctament.

 <img width="209" height="179" alt="Captura de pantalla de 2025-10-21 12-03-24" src="https://github.com/user-attachments/assets/3232658e-c307-49e2-a191-80c382788651" />
 
 <img width="567" height="475" alt="image" src="https://github.com/user-attachments/assets/cc8fbcc6-7aa7-4bd2-a3f6-3555b6cb708a" />

 **3.** Al comprobar que ho hem instal·lat correctament, ara procediré a eliminar el paquet o desintal·lar-lo. Per a això utilitzarè la commanda ----> apt-get remove. Utiltizaré aquesta perqué si tingués alguna configuració, no la borrariem per si la volem instal·lar en un futur, com pasaria amb la commanda "apt-get purge"

<img width="738" height="435" alt="image" src="https://github.com/user-attachments/assets/2be8528a-e7cf-4da6-a1c0-db3e99ae4513" />

- ### **Instal·lació amb el aptitude**

**1.** Primer instal·larem l'instal·lador aptitude amb la commanda ----> apt install aptitude.

<img width="710" height="154" alt="image" src="https://github.com/user-attachments/assets/c7694325-3798-4c03-ad05-02c06c5abfc9" />

**2.** Ara instal·larem el paquet Geany amb la comanda -----> aptitude install (paquet que volem instal·lar)

<img width="891" height="475" alt="image" src="https://github.com/user-attachments/assets/f764d323-89dc-43fb-a1a4-d21bb99f4ec0" />

**3.** Ara comprobem que efectivament ho hem instal·lat correctament visualitzant-ho al menu d'aplicacions i vuerem que s'executa correctament.

<img width="174" height="139" alt="image" src="https://github.com/user-attachments/assets/5cee2f14-c1be-42c1-b00c-ac09cc8955a6" />

<img width="904" height="639" alt="image" src="https://github.com/user-attachments/assets/17f0b0e0-07a9-4d95-aa8a-303ea941da5f" />

**4.** Al comprobar que ho hem instal·lat correctament, ara procediré a eliminar el paquet o desintal·lar-lo. Per a això utilitzarè la commanda ----> aptitude remove.

<img width="749" height="320" alt="image" src="https://github.com/user-attachments/assets/aae245e9-6fdc-403b-8056-70b5356e4e42" />

- ### **Instal·lació amb el dpkg**

**1.** Primer baixarem un paquet d'internet. Podem utilitzar la pàgina pag.pkgs.org. En aquest cas instal·lare el videojoc Pacman. Hem de tenir en compte que per a poder començar amb l'instal·lació, ens hem de posar per terminal dintre de la carpeta on el tenim baixat.

<img width="727" height="214" alt="image" src="https://github.com/user-attachments/assets/59f68339-e312-487a-a56a-17259d80d41e" />

**2.** Al tenir-lo ja instal·lat, procedirè a executar-ho des de la mateixa arrel solament posant el nom del paquet.

<img width="753" height="553" alt="image" src="https://github.com/user-attachments/assets/c4425db4-1b37-4403-b336-1027f09fc271" />

**3.** Ara solament ens queda desintal·lar-lo

<img width="733" height="156" alt="image" src="https://github.com/user-attachments/assets/b8f3b2e6-1892-4b95-9d27-c8c319d2d3fc" />

**4.** Per últim, comprobarem que ja no està instal·lat mitjançant la commanda de la fotografia següent. Sí el pacman segueix instal·lat, aquesta commanda ens el mostraria com a instal·lat.

<img width="748" height="39" alt="image" src="https://github.com/user-attachments/assets/513cbcc8-0fc1-4acb-ba2b-3f9e78383149" />

- ### **Instal·lació amb els repositoris**

**1.** Primer anirem a la pagina pkgs.org i anirem a l'apartat d'arxius .deb. En aquest cas escollirem el chrome.

<img width="1101" height="659" alt="image" src="https://github.com/user-attachments/assets/54b11753-c664-4f36-99a5-ee0a19e0f8e0" />

**2.** Ara descarguem el paquet .deb i nem mitjançant terminal al root de Descargues i fem un ls per veure que està baixat correctament

<img width="622" height="172" alt="image" src="https://github.com/user-attachments/assets/f4c2d8e5-39d5-4656-87b4-fbd9e8b5afbd" />

**3.** Procedim amb l'instal·lació amb la següent commanda:

<img width="1218" height="701" alt="image" src="https://github.com/user-attachments/assets/8a52d638-9392-4883-acdc-ddc4d7fc86d5" />

**4.** Ara comprobem que efectivament està instal·lat amb la commanda --version

<img width="1204" height="55" alt="image" src="https://github.com/user-attachments/assets/fe0b99af-6b7e-4ed2-82c5-c981d508d55c" />

**5.** Per últim, ara procediré amb el desinstal·lament amb la següent commanda:

<img width="1014" height="421" alt="image" src="https://github.com/user-attachments/assets/be79e535-86a9-4949-924f-9a54d36b8d98" />






 

 
