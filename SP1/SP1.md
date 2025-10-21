---
layout: default
title: "SP1 Avaluació, Instal·lació i Configuració de Xarxes i Sistemes Operatius"
---

# Virtualització i instal·lació del SO Ubuntu
## Virtualització

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


 ## Instal·lació

- En el moment de la instal·lació, ens demanarà l'idioma que volem escollir, després el tipus d'instal·lació que volem i el que ens interessa es l'opció de crear particions:

<img width="908" height="662" alt="image" src="https://github.com/user-attachments/assets/b2995272-1591-44da-a0cc-5d754c4e74d1" />

- Aquí procedim a dividir el disc sorbe les 80GB que hem escollit en el moment de la virtualització de la màquina virtual. Però com pròximament instal·larem amb aquestes 80GB el windows,
deixem 40GB a banda, que les destinarem per a l'instal·lació del Windows i les altres 40GB per a l'Ubuntu.

<img width="1282" height="865" alt="image" src="https://github.com/user-attachments/assets/5263f550-3d31-45dc-81b7-0f030162bf60" />

- El cas es que hem de pensar que sol tenim 40GB disponibles per a l'Ubuntu i per a repartir aquests per a la repartició que necessita Ubuntu per a la instal·lació. 
Primer dividirem 25 GB, per a l'arrel que es on van instal·lats els programes i el sistema.

<img width="862" height="649" alt="image" src="https://github.com/user-attachments/assets/cd540697-7714-4385-b25c-50a9d1bec1ed" />

- Ara destinarem 13GB per al /home, que es on van guardats els teus fitxers.

<img width="862" height="649" alt="image" src="https://github.com/user-attachments/assets/97b35073-988e-4867-9d5b-b3936b8d86f1" />

- Destinem 2GB per al /swap, que bàsicament es la memòria d'intercanvi.

<img width="862" height="649" alt="image" src="https://github.com/user-attachments/assets/713eb178-ab58-414b-a295-1555ee132615" />

- Agreguem aqui 1GB per a la EFI per a guardar el sistema d'arrancada.

<img width="862" height="649" alt="image" src="https://github.com/user-attachments/assets/e9925874-f2b4-4700-9dff-8cdc2dd35f9b" />

- Aqui fem l'última partició d'1GB per al BIOS boot

<img width="843" height="640" alt="image" src="https://github.com/user-attachments/assets/d3466d99-f3fe-4ba5-a556-e1fb692c969b" />

- Al haver creat totes les particions, li donem a instal·lar i escollirem el nostre usuari que personalitzarem escollint el nom que volem que sorti.

<img width="843" height="640" alt="image" src="https://github.com/user-attachments/assets/2193e1c0-98d8-4985-9e3f-27fbbdec916d" />














# Llicenciament








## Instal·lacions duals i gestors d'arrancada

- Aqui seleccionem el disc òptic per seleccionar l'ordre d'arrancada, sempre posant la memòria que ens demana mínima per a executar-ho. Després a "**Extended Features**", hem de posar l'opció activa EFI per a que s'executi Ubuntu bé després.

<img width="892" height="585" alt="image" src="https://github.com/user-attachments/assets/bf57659d-ba70-44be-a29d-b3365a813866" />

- Seleccionem la ISO de Windows que vam descarregar per determinar la partició que volem per a windows de la principal que vam fer anteriorment de 40GB

<img width="892" height="585" alt="image" src="https://github.com/user-attachments/assets/6a20b696-bcb3-4277-85e2-ce2cb5d40518" />

- Aquí escollirem la opció avançada d'instal·lació de Windows per a elegir la partició i creem la de 40GB que serà la meitat que vam destinar per a aquesta partició.

<img width="704" height="508" alt="image" src="https://github.com/user-attachments/assets/3eeddcd2-2d14-48d4-af4a-096f28a84dfa" />

- Després al acabar d'instalar-ho. Tancarem, anirem a paràmetres del client que hem creat del virtualbox d'ubuntu, i escollirem la iso del grub descarregada per a poder reparar el grub posteriorment.

<img width="875" height="556" alt="image" src="https://github.com/user-attachments/assets/9842beaf-981f-4fd4-9166-88c5a6d5d3dc" />

- Aquí executarem el client i li donarem varies vegades a la tecla "**ESC**" per a obrir la terminal de BIOS. Escollirem el BOOT Manager Menu i escollirem la següent ISO que es la del grub.

<img width="665" height="565" alt="image" src="https://github.com/user-attachments/assets/e0e99135-15c9-4c2c-8ac1-60e2895e0b59" />

- Després ens sortira aquest menú on escollirem l'opció "**Detect and show methods**".

<img width="665" height="565" alt="image" src="https://github.com/user-attachments/assets/94446828-6c6e-49ab-a731-89e7f2a49f8b" />

- Aquí escollirem el nostre línux que vam instal·lar per a procedir a reparar el grub.

<img width="665" height="565" alt="image" src="https://github.com/user-attachments/assets/d5af747c-93ec-4c09-87ba-437813bc3d71" />

- En el moment d'entrar a ubuntu, obrim la terminal. Escriurem la commanda " **sudo su**". Instal·larem  el paquet amb "**apt install efibootmgr**", després instal·lem "**apt install grub-efi**", després farem "**apt install --reinstall grub-pc**", Després d'haver ja creat el grub després posarem la commanda "**mkdir /boot/efi**". Posteriorment reinstal·lem el Grub a la unitat " **grub-install /dev/sda**" i "**grub-install --target=x86_64-efi --efi-directory=/boot/efi --bootloader-id=ubuntu**"
Aqui ara com veurem , mitjançant la commanda "**nano /etc/default/grub**", hem de fer varies coses per a acabar de restaurar el grub. Primer hem de comentar amb "**#**" el "**GRUB_TIMEOUT_STYLE=hidden**" i el "**GRUB_TIMEOUT=0**". Per últim descomentem treien "**#**" o si no ens surt escriure el text: "**GRUB_DISABLE_OS_PROBER=false**". Tanquem i guardem.

<img width="806" height="426" alt="image" src="https://github.com/user-attachments/assets/ed1e9d23-4ee3-4205-9439-c7ea08ae8406" />

- Aquí posarem la commanda "**update -grub**" per a tenir actualitzada la configuració que hem fet i poder veure que hem restaurat el grub. Però encara no hem acabat.

<img width="751" height="491" alt="image" src="https://github.com/user-attachments/assets/d30937d3-6c1e-47b3-962d-d26b0948e5b9" />

- Aquí obrim terminal una altra vegada per a veure la posició d'arranc del grub que tenim configurada. Però aquesta la tenim que canviar per a posar per a que al iniciar el virtualbox ens sorti el gestor d'arranc del grub i així poder escollir el SO que volem iniciar, si Ubuntu o WIndows.

<img width="751" height="491" alt="image" src="https://github.com/user-attachments/assets/c5d15e7d-44f1-479e-9597-013ccc5edace" />

- Per a que surti la posició de l'arranc que volem i compilar-la per a que ens surti al grub, hem de canviar la posició dintre del "**BootOrder**", fent que ubuntu sigui primer en el procés d'arranc del grub, perque sinó sempre començara iniciant windows primer. Després en la segona posició posem la iso del client del virtualbox i després posem les altres restants, sempre posant-les totes per a que no ens doni ningun tipus d'error. Després ho guardarem i ho tancarem.

<img width="595" height="216" alt="image" src="https://github.com/user-attachments/assets/9eef9635-a341-4f1e-a9a5-380a76584ec8" />

- Sí ho hem fet tot bé, al iniciar el client de virtual box ens tindria que sortir tal com la següent imatge.

<img width="823" height="518" alt="image" src="https://github.com/user-attachments/assets/aa413ced-c20b-4bd9-ad78-0fe2188e6df5" />


 # Particions i punts de restauració instantània
 - Primer anar a paràmetres del client creat d'Ubuntu, anar a emmagatzematge i crear un nou disc a la part dreta del controlador sata.
 
<img width="865" height="539" alt="image" src="https://github.com/user-attachments/assets/aa886bdc-c974-40b9-a79b-0fe58673699f" />

 - A Paràmetres canviem la xarxa a adaptador pont

<img width="865" height="539" alt="image" src="https://github.com/user-attachments/assets/e423645c-da76-4304-b974-fe682e712984" />

- Ara obrim terminal,posem sudo su.


<img width="865" height="539" alt="image" src="https://github.com/user-attachments/assets/7e3313cd-1235-4047-adb6-6ddf38243aae" />

<img width="833" height="585" alt="image" src="https://github.com/user-attachments/assets/43e77387-4b42-40a3-bb58-fe8bd3c1b397" />

<img width="717" height="220" alt="image" src="https://github.com/user-attachments/assets/af65e2af-79b9-4b60-bc3a-e995fdd2b858" />

<img width="717" height="416" alt="image" src="https://github.com/user-attachments/assets/7cf85d00-ae75-438c-a0cc-65cf8cfbdc79" />

<img width="742" height="461" alt="image" src="https://github.com/user-attachments/assets/c74c079d-0cc9-4542-ae7e-fb7fbbaf8b1e" />

<img width="577" height="253" alt="image" src="https://github.com/user-attachments/assets/a3238b6f-6a4e-4c46-9592-be7fa7c4817d" />

<img width="623" height="684" alt="image" src="https://github.com/user-attachments/assets/da64d79f-e5fc-4db8-9c8f-a31d6fad8840" />

<img width="623" height="684" alt="image" src="https://github.com/user-attachments/assets/fa2d5728-48f7-4d12-b082-bfef8c9604ff" />

<img width="623" height="684" alt="image" src="https://github.com/user-attachments/assets/1142b780-0529-48ec-a961-7d92ffad69a9" />

<img width="821" height="684" alt="image" src="https://github.com/user-attachments/assets/faab9a72-3f29-489b-926b-3c8179cde4ea" />

<img width="777" height="694" alt="image" src="https://github.com/user-attachments/assets/81163cca-f731-4dbf-bee5-75c1ff45b85b" />

<img width="766" height="651" alt="image" src="https://github.com/user-attachments/assets/745a95ed-6244-47ff-b41a-c88adcfc2f31" />

<img width="766" height="543" alt="image" src="https://github.com/user-attachments/assets/8c32f363-dd21-4463-919b-22fc719257f5" />

<img width="595" height="595" alt="image" src="https://github.com/user-attachments/assets/c4fbc6e2-4927-4f30-a7ca-059d51e6532b" />

<img width="716" height="240" alt="image" src="https://github.com/user-attachments/assets/b3385b5a-ca0f-47ee-9614-386f2bebfd1b" />



-




 # Configuració bàsica de la xarxa

- Primer comprovem la ip amb la commanda per terminal ubuntu ----> ip a.
- Després procedirem a canviar la nostra ip.
  <img width="1182" height="784" alt="image" src="https://github.com/user-attachments/assets/8728199b-49df-4188-9ae4-ca66b2cac6f2" />
  
  <img width="715" height="490" alt="image" src="https://github.com/user-attachments/assets/a101ce67-26be-4d13-be15-57919fcfab7c" />

  - Aquí amb el ping i un link d'internet veurem si s'ha aplicat bé la ip nova
  - 
  <img width="726" height="276" alt="image" src="https://github.com/user-attachments/assets/52a3cdcd-08d6-4a35-84a1-292b40afd5e7" />

  - Aquí amb el ping i la DNS veurem si s'ha aplicat bé la DNS nova
  
  <img width="725" height="226" alt="image" src="https://github.com/user-attachments/assets/ba2345d2-1fda-4234-8b44-0504bc0af0dc" />

  - Deixem la configuració de red com avans amb el DHCP automàtic

  <img width="591" height="473" alt="image" src="https://github.com/user-attachments/assets/027b93ab-5cfd-4c4a-9844-c0032b71002b" />

  - Fem el mateix pero mitjançant terminal

  <img width="782" height="501" alt="image" src="https://github.com/user-attachments/assets/54c49660-8e59-4118-bf35-eaa6cce70d81" />

  <img width="781" height="335" alt="image" src="https://github.com/user-attachments/assets/314a9e06-84e6-4d5d-abb7-4f8c90557cfc" />

  <img width="788" height="467" alt="image" src="https://github.com/user-attachments/assets/2969a426-ae15-4cbc-abd1-b42c4b158be8" />





 # Comandes generals i instal·lació de paquets


 

 
