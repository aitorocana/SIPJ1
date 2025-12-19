---
layout: default
title:**Sprint 2: Gestió de la Informació del Sistema i Administració
---

# **1.** Sistemes de fitxer i particions

- **Tipus de sistemes de fitxers** 

  **FAT:** Es compatible amb la majoria de OS degut a la seva simplicitat. Solen utilitzar-se a sistemes antics i usb's. No soporta permisos ni característiques avançades de seguretat. EL tamany màxim dels arxius FAT32 són 4B i el tamany màxim de les particions son de 2TB.

  **NTFS:** Es el sistema de fitxers que utiltiza windows. A diferència de l'anterior si que soporta particions molt més grans (16TB inclús  més) i permet xifrats de seguretat i permisos de seguretat per als arxius.

  **HFS+ / APFS:** EL HFS, era el sistema antic del OS de mac, però ara utilitzen el APFS. Una de les seves característiques es que està molt ben optimitzat per a les SSD i soporta xifrat natiu i clonació d'arxius

  **ext:** Es el sistema de fitxer que utilitza linux. La seva variant ext4 permet un major rendiment, un major tamany d'axius i de particions (fins a 16TB). Es compatible a linux de manera nativa i es caracteritza per la seva eficiencia.


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
  
### Comandes bàsiques per al formateig
  
Hem agregat una iso de 10GB
  
<img width="807" height="534" alt="image" src="https://github.com/user-attachments/assets/843977b2-0dcf-4ebb-939e-66367e32c272" />

Comprovem el disk que hem posat de 10GB

<img width="660" height="138" alt="image" src="https://github.com/user-attachments/assets/823f0d69-8075-4126-95cb-f5494ac19015" />

- Creem una partició de 4,8GB a /sdc1 

<img width="745" height="514" alt="image" src="https://github.com/user-attachments/assets/f8f2b1d4-f05a-47d5-b16a-bd0caccffeb6" />

- Partició de 5,2GB en /sdc2

<img width="846" height="535" alt="image" src="https://github.com/user-attachments/assets/cbfb7359-bd77-4460-b5c6-0affcebeff65" />

Per a guardar posar w a la terminal.

- Comprovarem les particions creades amb la commanda --->fdisk -l

<img width="840" height="264" alt="image" src="https://github.com/user-attachments/assets/f8308758-e407-4fb3-b14a-5b980f234cb1" />

Farem el block formateant la partició per a obtenir un tamany del block que no sigui el que ve per defecte.

<img width="840" height="264" alt="image" src="https://github.com/user-attachments/assets/4368500d-0b26-42d1-b423-0130c17bc66a" />

- Ara comprovem el tamany del block modificat a 2048

<img width="714" height="110" alt="image" src="https://github.com/user-attachments/assets/32599a26-af83-4478-86d8-ec6476a30df8" />

### GPARTED

* Ara amb el programa GParted que ja tenim instal·lat, elegim el sistema de fitxers per a la partició que ens faltaba formatar, es a dir la /sdc2.
  
<img width="1222" height="784" alt="image" src="https://github.com/user-attachments/assets/98dfb279-f2f7-4ccc-babe-990a5b94e1bd" />

<img width="876" height="602" alt="image" src="https://github.com/user-attachments/assets/52b5f861-7802-4d23-986e-6acfffb1dc87" />

- Creem un directori per a que la carpeta creada estigui apuntant a la particio1

<img width="744" height="256" alt="image" src="https://github.com/user-attachments/assets/8f858771-1bf6-4c3c-8d4d-1c9deebdc68a" />

Ara creo un nou arxiu:

<img width="744" height="256" alt="image" src="https://github.com/user-attachments/assets/a47b6fbc-e069-4fac-9fae-b0b5d5c09bf0" />

Fem un reboot i comprovem que passa. Com veiem, si introduim la commanda /mnt/particio1/ encara no estarà montada la partició. Per tant, a partir de la commanda ---> mount -t ext4 /dev/sdc1 /mnt/particio1/, ja estariem montant el sistema de fitxers dintre de la partició. Per aixó amb un ls dintre de la particio 1 ---> cd particio1/, si ens surt els següents fitxers, voldria dir que ja tenim montada correctament la partició.

<img width="744" height="256" alt="image" src="https://github.com/user-attachments/assets/b67a4dad-b4ab-41e8-bf0b-e3f72d96aacb" />

- El que hem fet aquí es agregar una linia al final de tot, especificant que la partició /sdc1 es monta de manera automàtica a ---> /mnt/particio1 amb el sistema de fitxers ext4.

<img width="737" height="404" alt="image" src="https://github.com/user-attachments/assets/ec032033-36c3-40c2-b5ae-5f96266796e0" />

Guardem lo d'avans i reboot per a comprovar si ens apareix la carpeta prova

<img width="682" height="174" alt="image" src="https://github.com/user-attachments/assets/07bd438b-a086-4cd2-8109-ac338d41e229" />

# **2.** Còpies de seguretat i automatització de tasques

- Primer que tot afegir dos discs de 1 gb cada un.

**1. Teoria còpies de Seguretat**

- Una còpia de seguretat
  diferents tipus: completa, diferencial i incremental

Una copia completa, es aquella que copia tot el disco, arxius, etc. L'inconvenient es que ocupen molt i son més lentes. Una copia diferencial, es aquella copia feta a partir de la diferencia de la completa, es a dir si faig una completa lo dilluns, i una diferencial lo dimarts, los arxius que es guardaran son els canviats de la diferencia entre el dilluns i dimarts. La copia incremental es la diferencia de la ultima incremental, es a dir, diluns creo una completa, lo dimarts tinc una incremental i, el dimecres si faig una altra, aquesta copia guardaria la diferencia de la copia del dimarts.

| **Tipus de còpia**    | **Què copia?**                                                                        | **Avantatges**                                                                                 | **Inconvenients**                                                           |
| --------------------- | ------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------- |
| **Còpia completa**    | Totes les dades del sistema: discs, arxius, carpetes, etc.                            | Molt fiable; còpia independent; restauració molt ràpida.                                       | Ocupa molt espai; temps de còpia més lent.                                  |
| **Còpia diferencial** | Copia tots els canvis respecte l'última còpia completa.                               | Més ràpida i ligera que la completa; restauració ràpida (només completa + última diferencial). | Cada dia ocupa més espai perquè acumula tots els canvis des de la completa. |
| **Còpia incremental** | Copia únicament els canvis respecte l'última còpia (ja sigui completa o incremental). | Ocupa molt poc espai; molt ràpida de crear.                                                    | Restauració més lenta (cal la completa + totes les incrementals).           |


**2. Teoria comandes Backups**
   - cp: es una copia simple, no intel·ligent i nomes s'utilitza en sistemes locals
   - rsync: es per a sincronitzar carpetes i es intel·ligent, permet fer copies en local o en remot via ssh
   - dd: no es per a fer copies, es per a clonar particions o discos. No es intel·ligent.
   
**3. Pràctica comandes Backups**

- Montem els disc amb fdisk /dev/sdd i el sde. Després formatem amb mkfs.ext4 /dev/sdd1 i sde1 (particions). 

<img width="617" height="415" alt="image" src="https://github.com/user-attachments/assets/3e8d2693-7d96-4ff9-9c7f-20d245514e1b" />

- Ara acabem de montar un disc:

<img width="805" height="433" alt="image" src="https://github.com/user-attachments/assets/1ecdf431-7745-4df2-b86d-d886790d6ffe" />

------------------------------

**- cp:**
     
<img width="918" height="690" alt="image" src="https://github.com/user-attachments/assets/2846b295-29c7-4805-a65c-6fcffd2c79e2" />

------------------------------

**- rsync:**

 <img width="933" height="502" alt="image" src="https://github.com/user-attachments/assets/07884d7f-b4a4-409d-8135-98b9e1a824b1" />

 ------------------------------

**- dd:**

<img width="933" height="502" alt="image" src="https://github.com/user-attachments/assets/c991ed11-2495-4067-bdad-0c5c7e967fb7" />

------------------------------


     
**4. Pràctica programes Backups** /////////FER-HO  A CASA, INSTAL·LAR UN PROGRAMA DE BACKUPS I FER ELS TIPUS DE COPIA DE SEGURETAT ---> NORMAL, INCREMENTAL, DIFERENCIAL

   **- Duplicity**: El primer pas, es instal·lar el programa i comprovar que s'ha instal·lat correctament.
   
   <img width="722" height="190" alt="image" src="https://github.com/user-attachments/assets/f0547cdd-d812-4a95-864e-b0de5e7e7d0e" />

   **4.1 Còpia normal**

- Ara que el tenim instal·lat, el que s'ha de fer es crear un directori, per a guardar les copies de seguretat. A més, crearem un directori i un arxiu buit dintre d'ell, per a poder fer un exemple de còpia complet. Després es procedeix en copiar completament el directori dintre del directori destinat per a les còpies de seguretat. 

<img width="918" height="499" alt="image" src="https://github.com/user-attachments/assets/072a4ddd-2684-4dc1-bb0a-7d2615fca4b7" />

   **4.2 Còpia incremental**

- Ara crearé un altre arxiu per a poder provar la còpia incremental. Però ara, en el moment de crear la còpia de seguretat del directori que he creat, es fa amb la mateixa commanda de la còpia normal, però sense el full.

<img width="918" height="499" alt="image" src="https://github.com/user-attachments/assets/20dbd9a4-8c32-4ba5-8219-30b100e6faf8" />

- Per a comprovar que s'han fet correctament, fariem la següent commanda:

<img width="914" height="353" alt="image" src="https://github.com/user-attachments/assets/3b187b23-9b57-4dd7-9a8f-4397585cd71e" />

   **4.3 Còpia diferencial**

- Per a fer una còpia diferencial, modificaré o crearé algo de text a algun arxiu que he creat, a banda dels arxius que ja tinc creats. Mitnjançant aquest tipus de còpia, se guardaran els canvis que s'han det des de la última còpia COMPLETA o normal. Per tant, se guardaran els fitxers canviats.

<img width="1014" height="559" alt="image" src="https://github.com/user-attachments/assets/914017fd-b28a-47fd-8458-f281a2bf7be4" />

- Ara ho comprovem, i veiem que ens surt una altra còpia incremental, però realment es la diferencial, l´unic que la aplicació sol coneix dos tipus de backups, el complet i el incremental. Però al ús es una còpia diferencial.

<img width="921" height="370" alt="image" src="https://github.com/user-attachments/assets/dc11ea02-a81d-41de-ab8a-e5aee26b39f0" />


**5. Teoria automatització scripts, cron i anacron**

scripts, que es i para que serveix: Es un fitxer executable que serveix per a fer moltes tasques. Es poden utilitzar amb diferents llenguatges

cron: Serveixen per a programar la temporització dels Scripts, es a dir, per a decidir quan s'executen els scripts. El cron s'utilitza normalment per a automatitzar tasques per a usuaris particulars en una data i una hora concrets i, si en aquell moment que la tasca esta programada, l'ordenador esta tancat, la tasca es perd.

anacron: Serveix per al mateix, pero es diferencia perque la tasca no es perd perque quan s'encen l'ordenador anacron recupera aquestes tasques.

Antigament anaven per separat, però ara ja treballen conjuntament.

- FItxers importants per a configurar cron i anacron:

  <img width="933" height="502" alt="image" src="https://github.com/user-attachments/assets/fbab62a0-8737-48b3-8c9a-fa5dbd44a7b1" />

  <img width="874" height="288" alt="image" src="https://github.com/user-attachments/assets/61695852-e9d6-469d-a450-aab38ad35d4c" />

  <img width="874" height="288" alt="image" src="https://github.com/user-attachments/assets/c1b437b6-7b4b-4d07-9f6c-8918d0170e25" />

  <img width="874" height="288" alt="image" src="https://github.com/user-attachments/assets/51f6c37e-457e-4672-bd05-e9a8b67e69b1" />

     
**6. Pràctica automatització**

   - cron

<img width="874" height="288" alt="image" src="https://github.com/user-attachments/assets/bb5b487b-f6c6-41b9-bec6-5c4d61f9a799" />

<img width="846" height="611" alt="image" src="https://github.com/user-attachments/assets/2bc3ae65-c8c1-4e55-a71c-63be3c1d7c93" />

<img width="943" height="582" alt="image" src="https://github.com/user-attachments/assets/4f818f37-29b4-488e-80cc-876aefdd8986" />

<img width="147" height="150" alt="image" src="https://github.com/user-attachments/assets/cb057b39-3ceb-4d41-9140-cd6489458590" />

<img width="608" height="430" alt="image" src="https://github.com/user-attachments/assets/0ddeb610-24ae-4804-af45-ed5e8f98b8d4" />


   - anacron

COmento la ultima linia

<img width="941" height="443" alt="image" src="https://github.com/user-attachments/assets/001e4ca6-2c23-44e9-824a-e32c6e5c0363" />

<img width="938" height="188" alt="image" src="https://github.com/user-attachments/assets/80a2c888-6937-4423-a2fd-f2c3a58465f5" />

<img width="962" height="336" alt="image" src="https://github.com/user-attachments/assets/09dd6d70-e8b0-4c03-ba45-e7d69e00b113" />

<img width="962" height="336" alt="image" src="https://github.com/user-attachments/assets/be492704-c4c7-496e-b34b-383158e2b570" />

<img width="962" height="336" alt="image" src="https://github.com/user-attachments/assets/91d8dc00-5e1a-4eb8-bead-e766c2b1e0b7" />

Borrem el tar que teniem al escriptori, reiniciem la màquina i veurem que ens apareix el tar sol en 1 min ja que es el que hem modificat al anacron.

<img width="1203" height="615" alt="image" src="https://github.com/user-attachments/assets/9338a156-6d6f-415f-84f6-67c60e251796" />





# **3.** Gestió d'usuaris, grups i permisos

**3.1** Fitxer implicats (en trobarem 4): 

Primer que tot ens fiquem amb el sudo su, a la carpeta etc ---> cd /etc i despres fem aixó---->nano passwd (primer fitxer implicat), que trobarem tots els usuaris que hi han. el "1000", es el usuari i el segon 1000, es el gitnumber que es el grub que s'ha assignat a 'usuari, i aquest sera el grup principal. 

<img width="750" height="395" alt="image" src="https://github.com/user-attachments/assets/f928f9a0-43b6-4ac1-8549-b862038d0b47" />

- Després amb el **nano group:** Veiem tots els usuaris que formen part d'un grup.
  
 <img width="744" height="450" alt="image" src="https://github.com/user-attachments/assets/9201be1d-18df-4d0e-bc31-7c52b0af35c1" />

-**nano shadow:** Veurem lo referent a lo que son contrasenyes i caducitats de les contrasenyes. EL que podem veure exactament referent a la caducitat de les contrasenyes, es que a cada camp es pot observar el màxim de dies avans de que s'expiri la contrasenya (99999) seguit amb els dies d'avís avans d'expirar aquesta (7). 
  
  <img width="744" height="450" alt="image" src="https://github.com/user-attachments/assets/c480a490-c719-49c3-9b16-32eb5605ffc0" />

- **nano gshadow:** tambe veurem els usuaris que formen part d'un grup, pero es diferència amb el grup en que podem veure qui es l'usuari administrador del grup, on s'indica el (cdrom:*)
  
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

* DHOME=/var

<img width="817" height="496" alt="image" src="https://github.com/user-attachments/assets/251ac437-dd37-4179-bec7-d30267aacc37" />

* DHOME=/var ---> transformat o canviat a /home + canvi del first UID I GID que es per a canviar l'assignacio del nostre usuari

<img width="743" height="403" alt="image" src="https://github.com/user-attachments/assets/109d5353-f0ff-46c0-bc05-662c38095038" />

<img width="817" height="496" alt="image" src="https://github.com/user-attachments/assets/2d82c125-8ce2-49f8-a407-6a4ac3ee0e26" />

- Creació del nou usuari per a comprovar la modificació del home.

<img width="696" height="332" alt="image" src="https://github.com/user-attachments/assets/329d1857-3b15-462d-b801-58c0d091aca2" />

- Accedim al home, i veiem el nou usuari creat "aitoreta"

<img width="665" height="139" alt="image" src="https://github.com/user-attachments/assets/d36c1a01-ecaf-4a27-b978-85f554299683" />

- si vull canviar caducitats de contrasenyes ----> sudo nano /etc/login.defs:
  
<img width="732" height="442" alt="image" src="https://github.com/user-attachments/assets/bc764535-b9c8-42e4-94cd-67e4d7c374fb" />

- Si vull canviar o assignar un shell per defecte, amb la commanda ----> sudo nano /etc/useradd.conf
  
<img width="873" height="605" alt="image" src="https://github.com/user-attachments/assets/f2398664-0e72-40d1-986d-71f5aa1e28f1" />

* Comprovem aquesta assignació del SHELL creant un nou usuari
  
<img width="748" height="103" alt="image" src="https://github.com/user-attachments/assets/1ca6d91a-b9f9-4e31-8d7c-a9f2a7b97e04" />

----------------------
- Ara pasem a la edició del /etc/skel/.profile per a que cada vegada que entresim des de la terminal a l'usuari creat nou, ens mostri un missatge personalitzat

<img width="668" height="149" alt="image" src="https://github.com/user-attachments/assets/25e26eea-c1bc-4cf6-9d58-84376f19fa79" />

Comprovació:

<img width="706" height="180" alt="image" src="https://github.com/user-attachments/assets/44146a52-1a0b-4886-9ef6-9dc5d9db8b63" />

- Ara editarem el bash a /etc/skel/.bashrc , per a tenir-ho personalitzat inclus per als nous usuaris.

<img width="745" height="383" alt="image" src="https://github.com/user-attachments/assets/a76da8e0-0b7a-4ae4-8d08-c0a3e13bf3b4" />

Comprovació:

<img width="745" height="383" alt="image" src="https://github.com/user-attachments/assets/293715c4-fc71-488f-9767-ec5245c5d1a0" />

- Ara editarem el /etc/skel/.bash_logout, per a que ens mostri un missatge personalitzat a l'hora de surtir de la sessió oberta.

<img width="745" height="383" alt="image" src="https://github.com/user-attachments/assets/e130d847-d928-48ba-8a39-e71c9236e14d" />

Comprovació:

<img width="721" height="440" alt="image" src="https://github.com/user-attachments/assets/78b4ad15-c8de-4c9d-a486-c24233eac465" />

-------
**Ubuntu server**
  
- Des d'ubuntu server amb el control dret +f5, comprovar l'usuari creat nou amb la carpeta que hauré modificat com a home, aqui veurem si el usuari nou, ha agarrat tots els arxius editats al skel. Veiem que a partir de la creació d'aquest nou usuari, s'han passat totes les modificacions del .profile, .bashrc i del .bashlogout:

<img width="1035" height="760" alt="image" src="https://github.com/user-attachments/assets/311b95a5-3eb9-4540-ba12-8b52d5bdbfcd" />

- Per ultim entrarem a la carpeta Imágenes o la que haurem dit, amb cd Imágenes/, crear una carpeta buida amb touch i el nom de la carpeta, comprovar amb ls si la hem creada, fer exit de la terminal, i control dret + f2 per a sortir.



# **4.** Gestió de permissos

**1. UOG**

- Creem una carpeta i un arxiu. ELs permissos es veuen a l'esquerra, en un arxiu rw vol dir que l'usuari pot accedir, borrar, etc.

<img width="741" height="496" alt="image" src="https://github.com/user-attachments/assets/1d7d7ca2-9556-49c0-adda-4b3fc111b7e1" />

- Volem modificar permisos. Primer creem 4 usuaris.

<img width="743" height="126" alt="image" src="https://github.com/user-attachments/assets/c3234ff5-598e-44a7-b29e-09fd501cc424" />

- Creem un grup i posem dintre del grup dos usuaris.

<img width="745" height="227" alt="image" src="https://github.com/user-attachments/assets/b65cbff9-7e34-4c43-95df-18889cd61701" />

- Creem

<img width="692" height="264" alt="image" src="https://github.com/user-attachments/assets/9f40a045-b14a-497e-be61-d072f92c78c9" />

<img width="685" height="52" alt="image" src="https://github.com/user-attachments/assets/6d62e76d-5c16-4c8b-b7e6-7c4028fbb0d4" />

- Cambiem el propietari a groc, el que volem es que lo usuari que resta dels 4 creats que ni es propietari ni forma aprt del grup no pugui accedir. Amb el sistema octal, cambiem els permisos per a que el usuari que resta no pugui ni accedir.

<img width="668" height="239" alt="image" src="https://github.com/user-attachments/assets/d7ec0d33-6cb2-4327-aaea-e606732fbe19" />

-**Proves dels permisos:** Primer provem que groc te tots els permisos.

<img width="680" height="251" alt="image" src="https://github.com/user-attachments/assets/0c609d98-0693-4e9f-b43d-3051775abb20" />

- Provo permisos de un usuari del grup creat, i observem que no podem ni entrar ni borrar

<img width="718" height="303" alt="image" src="https://github.com/user-attachments/assets/36610eca-65a9-482c-b7e6-0687586695e4" />

- Provo permisos del verd que es qui no te permisos teoricament (com podem veure s'ha denegat tot).

<img width="702" height="246" alt="image" src="https://github.com/user-attachments/assets/c5487675-238c-4c22-b779-9b0be83b09ff" />

**2. ACL (llistes de control d'accés)**

- Ara creo un altre usuari... Morat. volem crear una llista d'exepcio per a que aquest usuari tingui permisos excepcionalment

<img width="699" height="171" alt="image" src="https://github.com/user-attachments/assets/04a8b34a-f3dd-4896-bef4-ff269a76c9d4" />

- Ara crearem la exepcio modificant els permissos sol per a aquest usuari. Veiem que amb el simbol + després dels permisos ---, la exepcio ha sigut creada.

<img width="729" height="261" alt="image" src="https://github.com/user-attachments/assets/e31b1db3-7c2b-4edd-a6ef-36388d8992a4" />

- Prova del usuari morat que te tots els permisos

<img width="725" height="261" alt="image" src="https://github.com/user-attachments/assets/c15dcfe1-7a7e-4d14-a301-89a1d691e958" />

- Ara crearé una exepció però denegant que un del usuari del grup, no pugui accedir ni res, traent-li tots els permissos

<img width="740" height="236" alt="image" src="https://github.com/user-attachments/assets/4d0ca9fe-9483-4769-b7ca-6a67af3e06f5" />

- Ara ho provem. Veiem que funciona.

<img width="731" height="204" alt="image" src="https://github.com/user-attachments/assets/0895dc8e-9c36-439e-ba3c-c46aad37b1ac" />

- Volem reestablir les exepcions netejant les que hem creat.
  
<img width="733" height="218" alt="image" src="https://github.com/user-attachments/assets/79eeff20-b946-48d4-8f48-5a64f61b3a76" />

- Ara vull fer una carpeta compartida per a tots. Primer farem que per al root, tots els usuaris creats tinguin tot els permisos

<img width="733" height="218" alt="image" src="https://github.com/user-attachments/assets/b537ef45-b99a-4c1e-9720-c7f8fdad3c89" />

- Veiem que blau te tots els permisos, tant ell com els altres també els tindran

<img width="750" height="378" alt="image" src="https://github.com/user-attachments/assets/8efc1d92-1541-479a-8214-d4e70240cef1" />

- Però el que tindria que fer cada usuari, es poder fer de tot pero solament borrar lo referit a les seves propies carpetes. Amb això es fara un permis especial amb el sticky. Aqui cambiem la x de others per la t

<img width="737" height="127" alt="image" src="https://github.com/user-attachments/assets/996253d1-0e6f-4356-ad43-c170bac309d2" />

- Comprovació:

<img width="740" height="346" alt="image" src="https://github.com/user-attachments/assets/1e8d8ff9-2b4e-4a12-9b31-fb411b05262d" />

5. Gestió de processos



