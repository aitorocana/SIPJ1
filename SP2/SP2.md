---
layout: default
title:**Sprint 2: Gestió de la Informació del Sistema i Administració**
---

# **1.** Sistemes de fitxer i particions**

## **1.2.** Mida del sector:
Un sector es la unitat minima física on se guarden les dades en un disc. Per defecte son 512 bytes (en principi no es modificable aquesta mida).

Per a saber la mida del sector fem a terminal la comanda fdisk -l
<img width="764" height="226" alt="image" src="https://github.com/user-attachments/assets/e60dd484-035f-4ee1-81ae-876b97c9f68c" />

## **1.3.** Mida del block:
Es la unitat minima lògica de com se guarden les dades a nivell de sistema operatiu. Per defecte son 4096 bytes (Sí es modificable aquesta mida quan formatem la partició). Equivaldria a 8 sectors.

Aquí localitzem la partició:

<img width="725" height="125" alt="image" src="https://github.com/user-attachments/assets/07e62e14-f7dd-4790-8e07-c014edeef5a0" />

i ara mirarem la mida de la nostra partició:

<img width="758" height="128" alt="image" src="https://github.com/user-attachments/assets/b980d1a6-da1e-4565-a3ae-ab27601d46ed" />

Amb la commanda du -b div.txt comprobem la mida d'un fitxer. Però realment amb la du -sh div.txt, veurem realment que agarra la mida 

<img width="647" height="391" alt="image" src="https://github.com/user-attachments/assets/b181b212-07ae-43d1-a604-c1b5f3acdb9e" />

## **1.4.** Fragmentació interna

Es tot aquell espai desaprofitat de disc dels blocs que no estem usant. Per tant modificant el tamany del block i reduint-lo (sempre després d'haver fet un formateig), podem aprofitar l'espai que en principi astava desaprofitat. Però podria suposar una reducció en el rendiment del sistema degut a que el sistema esta llegint moltes més particions.

## **1.5.** Fragmentació externa

Es quan a mesura que anem treballant amb el SO, ya els arxius no queden guardats en blocs continuos de memòria i el rendiment llavors baixa. Amb el desfragmentador de discs (amb WIndows) podem reduir aquesta fragmentació externa. En linux diuen que el seu sitema de fitxers es tan bo que no caldria un desfragmentador de fitxers.

Amb aquesta commanda veurem si necessito desfragmentar ----> e4defrag -c /dev/sdb2

<img width="807" height="534" alt="image" src="https://github.com/user-attachments/assets/276ee9b8-dbcf-499f-a798-10aa572a7569" />

Amb aquesta començaria a desfragmentar ----> e4defrag /dev/sdb2

<img width="807" height="534" alt="image" src="https://github.com/user-attachments/assets/e5f98be7-585a-4bc4-a6ad-2486e181504b" />

Si utilitzem el sistema de fitxer de ntfs, ho podrem utilitzar per a windos i ubuntu jutnament. Els més coneguts a part, som fat32 i ntfs. d'altra banda estirà el ntfs.

## **1.6.** Tipus de formateig

- Alt nivell: No es borren els arxius ensi en aquest formateig, sinò que es borra el sistema de fitxers. Per tant sempre es podria recuperar les dades.
- Mig nivell: No es borren els arxius ensi en aquest formateig, sinò que es borra el sistema de fitxers, però també va mirant els sectors a nivell de disc i els marca si hi ha algun defectuos.
- Baix nivell: Amb aquest si que borraries tots els arxius i tot, però sol es pot fer amb programes específics.

## **1.7.** Particions/volums

Una partició bàsicament es una divisió que fem al disc per a separar-ho en parts a nivell físic.

Un volum es com una capa d'abstracció lògica que es posa per damunt de les particions que agrupa les particions i/o discs.

* ### GPARTED

 Així elegim el sistema de fitxers per a la partició que ens faltaba formatar
  
<img width="1222" height="784" alt="image" src="https://github.com/user-attachments/assets/98dfb279-f2f7-4ccc-babe-990a5b94e1bd" />

<img width="876" height="602" alt="image" src="https://github.com/user-attachments/assets/52b5f861-7802-4d23-986e-6acfffb1dc87" />

comprovem el tamany del block

<img width="714" height="110" alt="image" src="https://github.com/user-attachments/assets/32599a26-af83-4478-86d8-ec6476a30df8" />

Ara hem fet que la carpeta creada estigui apuntant a la particio1

<img width="744" height="256" alt="image" src="https://github.com/user-attachments/assets/8f858771-1bf6-4c3c-8d4d-1c9deebdc68a" />

Ara creo un nou arxiu:

<img width="744" height="256" alt="image" src="https://github.com/user-attachments/assets/a47b6fbc-e069-4fac-9fae-b0b5d5c09bf0" />

Fem un reboot i comprovem que passa:

<img width="744" height="256" alt="image" src="https://github.com/user-attachments/assets/b67a4dad-b4ab-41e8-bf0b-e3f72d96aacb" />

<img width="737" height="404" alt="image" src="https://github.com/user-attachments/assets/ec032033-36c3-40c2-b5ae-5f96266796e0" />

Guardem lo d'avans i reboot per a comprovar si ens apareix la carpeta prova

<img width="682" height="174" alt="image" src="https://github.com/user-attachments/assets/07bd438b-a086-4cd2-8109-ac338d41e229" />

  
* ### Comandes

  
<img width="807" height="534" alt="image" src="https://github.com/user-attachments/assets/843977b2-0dcf-4ebb-939e-66367e32c272" />

Comprovem el disk que hem posat de 10GB

<img width="660" height="138" alt="image" src="https://github.com/user-attachments/assets/823f0d69-8075-4126-95cb-f5494ac19015" />

<img width="745" height="514" alt="image" src="https://github.com/user-attachments/assets/f8f2b1d4-f05a-47d5-b16a-bd0caccffeb6" />

<img width="846" height="535" alt="image" src="https://github.com/user-attachments/assets/cbfb7359-bd77-4460-b5c6-0affcebeff65" />

Per a guardar posar w a la terminal.

Comprovarem les particions creades amb la commanda --->fdisk -l

<img width="840" height="264" alt="image" src="https://github.com/user-attachments/assets/f8308758-e407-4fb3-b14a-5b980f234cb1" />

Farem el block

<img width="840" height="264" alt="image" src="https://github.com/user-attachments/assets/4368500d-0b26-42d1-b423-0130c17bc66a" />


# **2.** Còpies de seguretat i automatització de tasques**1.**


# **3.** Gestió d'usuaris, grups i permisos

**3.1** Fitxer implicats (en trobarem 4): 

Primer que tot ens fiquem amb el sudo su, a la carpeta etc ---> cd /etc i despres fem aixó---->nano passwd (primer fitxer implicat), que trobarem tots els usuaris que hi han. el "1000", es el usuari i el segon 1000, es el gitnumber que es el grub que s'ha assignat a 'usuari, i aquest sera el grup principal. 
<img width="750" height="395" alt="image" src="https://github.com/user-attachments/assets/f928f9a0-43b6-4ac1-8549-b862038d0b47" />

- Després amb el nano group: Veiem tots els usuaris que formen part d'un grup . 
 <img width="744" height="450" alt="image" src="https://github.com/user-attachments/assets/9201be1d-18df-4d0e-bc31-7c52b0af35c1" />

- nano shadow: Veurem lo referent a lo que son contrasenyes i caducitats de les contrasenyes. *IMPORTANT*"""BUSCAR UNA MICA CADA CAMP Q ERA"""
  <img width="744" height="450" alt="image" src="https://github.com/user-attachments/assets/c480a490-c719-49c3-9b16-32eb5605ffc0" />

- nano gshadow: tambe veurem els usuaris que formen part d'un grup, pero es diferència amb el grup en que podem veure qui es l'usuari administrador del grup, on s'indica el (cdrom:*)
  <img width="744" height="450" alt="image" src="https://github.com/user-attachments/assets/201615a4-59ee-44b7-8162-f71125328a66" />


**3.2** Comandes bàsiques

- Fer ----> adduser per a crear un nou usuari

 <img width="736" height="317" alt="image" src="https://github.com/user-attachments/assets/31b41c55-bb70-447d-bbb8-b67c5afeb117" />

- Entrar dintre del usuari creat nou "ocanya" per a accedir gràficament i comprovar-ho amb un ls ocanya/. Però com vam canviar la home per var, doncs tindrem que accedir als usuaris a partir de la root var ---> cd var/

<img width="737" height="193" alt="image" src="https://github.com/user-attachments/assets/af63a999-22ea-4c07-9536-2dba19231da3" />

- Crear usuari amb el ---> useradd (de manera més manual al adduser). Amb les commandes següents modificariem el shell i li creariem la carpeta home. Per últim amb el chown li pasarem els permisos root al usuari.
  
<img width="652" height="173" alt="image" src="https://github.com/user-attachments/assets/e32bcb7d-58eb-49bc-b531-f415c2a61835" />

<img width="651" height="77" alt="image" src="https://github.com/user-attachments/assets/bc406508-284a-4874-9605-645a91700268" />


- Comprovariem amb un ls a la root que vam declarar var/ si s'ha creat l'usuari abril.

<img width="651" height="92" alt="image" src="https://github.com/user-attachments/assets/0f918907-c5f5-43db-80a2-1744fe8731b2" />

------------------------

- Ara procedirem a veure com es borren usuaris. Primer crearem 4 usuaris i els borrarem de dues formes. Els usuaris seran ocanya 1,2,3 i 4.

- 1. borrar amb deluser:

     <img width="687" height="76" alt="image" src="https://github.com/user-attachments/assets/7af3d33a-3297-4fcb-861b-fcf8710b75a2" />


- 2. borrar amb uderdel -l: 

     <img width="456" height="27" alt="image" src="https://github.com/user-attachments/assets/eff2877c-71ca-4c11-a8af-82425ffd4e3a" />
     
----------------------------------

- Per a bloqueijar un usuari ----> usermod -L (usuari):

  <img width="739" height="78" alt="image" src="https://github.com/user-attachments/assets/15edc76b-6374-464d-8ce2-14b6789127df" />

- Per a desblocarlo ----> usermod -U (usuari):

  <img width="739" height="78" alt="image" src="https://github.com/user-attachments/assets/08674a8c-8f2d-4ba3-bd1f-0de65b110a05" />
  
------------------------------

- Ara crearem un grup de usuaris:

<img width="739" height="78" alt="image" src="https://github.com/user-attachments/assets/ced3a8c0-d32d-4bb3-b8e9-37b27a88e466" />

<img width="734" height="115" alt="image" src="https://github.com/user-attachments/assets/5b804887-7590-4246-97bd-acb57dbaf61b" />


- Hi han 3 maneres de agregar usuaris al grup que acabo de crear, tot aixó havent creat nous usuars anteriorment:
  
<img width="761" height="233" alt="image" src="https://github.com/user-attachments/assets/13aac96a-53d9-4433-86c6-44181fe326fc" />

- ara voldrem borrar usuaris del grup:
  
<img width="748" height="144" alt="image" src="https://github.com/user-attachments/assets/05fa5a57-20fe-4f0b-9fcf-1f205bcc5b90" />

- Amb la comanda -g serveix per a modificar el grup principal de l'usuari.

<img width="752" height="159" alt="image" src="https://github.com/user-attachments/assets/2293075b-b72f-4284-9868-9c5a65ee393b" />

- Amb això veurem a quins grups pertany l'usuari
  
<img width="727" height="97" alt="image" src="https://github.com/user-attachments/assets/160c48f1-5027-493a-9927-bd2aa576475e" />

- Ara borrarem el grup, pero observem que tenim un grup principal, cosa que haurem de borrar que sigui el grup primari o principal i després ja podrem borrar el grup.

<img width="708" height="258" alt="image" src="https://github.com/user-attachments/assets/b8f9ed23-0e42-4c82-b807-753f8fbf6ce4" />

--------------------- 

- Ara el que voldrem serà modificar la comanda skel que va associada al que fa la commanda adduser. Primer que tot hem de crear dintre del directori SKEL, dos fitxers: acces_directe i fitxer_compartit

<img width="873" height="605" alt="image" src="https://github.com/user-attachments/assets/c15bb3a6-fed4-424d-83b8-66ea5708d6cd" />

Ara que tenim creats aquests fitxers, hauriem de comprovar si per als nous usuaris, aquests apareixen comprovant-ho mostrant l'usuari. (proves de que ha funcionat la creació dels fitxers anteriors amb la creació d'un usuari adduser:)

<img width="878" height="630" alt="image" src="https://github.com/user-attachments/assets/98dbc21e-54dc-45bf-9e46-3ecb7fe3db4a" />

---------------------------------------------------------------------------------------------

**3.3** Personalització de comandes

- Primer que tot si vull modificar la commanda adduser ----> entrariem amb "sudo nano /etc/adduser.conf", Aqui podem canviar el DHOME, per la que volessim. Aquesta modificació seria el nostre home per a un nou usuari creat. Per tant, canviarem el DHOME /var i el tornarem a ficar /home. Després, canviem el first UID I GID que es per a canviar l'assignacio del nostre usuari.

DHOME=/var

 <img width="817" height="496" alt="image" src="https://github.com/user-attachments/assets/251ac437-dd37-4179-bec7-d30267aacc37" />

DHOME=/var ---> transformat o canviat a /home

<img width="743" height="403" alt="image" src="https://github.com/user-attachments/assets/109d5353-f0ff-46c0-bc05-662c38095038" />





 <img width="817" height="496" alt="image" src="https://github.com/user-attachments/assets/2d82c125-8ce2-49f8-a407-6a4ac3ee0e26" />



- si vull canviar caducitats de contrasenyes de adduser i useradd:
<img width="873" height="605" alt="image" src="https://github.com/user-attachments/assets/e810c3b9-c8d7-4e54-bf33-fdff13dc6837" />


- Amb axò canvio a bash
<img width="873" height="605" alt="image" src="https://github.com/user-attachments/assets/f2398664-0e72-40d1-986d-71f5aa1e28f1" />



- Ara comprovem useradd
  
<img width="877" height="119" alt="image" src="https://github.com/user-attachments/assets/b91d873a-1808-45c2-a5a5-532689501ff8" />


- fer ls -la i fer una prova


EXEMPLE MEU
EXEMPLE MEU
EXEMPLE MEU
-------
FER AIXÓ SEGÜENT I BORRAR LO QUE PERTANY A AIXÒ DE LES PROVES ANTERIORS DE EXEMPLE, OSIGUE BORRAR LES PROVES ANTERIORS PER A POSAR EL MEU EXEMPLE.

**EXERCICI PROVA ADDUSER I USERADD EN UNA PROVA FETA PROPIA**, després d'haver creat les modificacions del usuari (REPLICANT TOT LO ANTERIOR), doncs canviar coses amb el nano.profile, nano.bashrc, nano .bash_logout i també  desde ubuntu server amb el control dret +f5, comprovar l'usuari creat nou amb la carpeta que haurie modificat com a home, si surten les modificacions del nano que acabo de nombrar.:

<img width="1035" height="760" alt="image" src="https://github.com/user-attachments/assets/311b95a5-3eb9-4540-ba12-8b52d5bdbfcd" />

- Per ultim entrarem a la carpeta Imágenes o la que haurem dit, amb cd Imágenes/, crear una carpeta buida amb touch i el nom de la carpeta, comprovar amb ls si la hem creada, fer exit de la terminal, i control dret + f2 per a sortir.



 


- 

# **4.** Gestió de procesos
