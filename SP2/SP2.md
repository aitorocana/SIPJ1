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
  
<img width="744" height="450" alt="image" src="https://github.com/user-attachments/assets/295568da-1dad-4657-beac-abc749da1c60" />

- Entrar dintre del usuari creat nou "ginas" per a accedir gràficament i comprovar-ho amb un ls ginas/
  
  <img width="657" height="133" alt="image" src="https://github.com/user-attachments/assets/2f770d35-48f9-4456-b613-3375e4256a5c" />

- Crear usuari amb el ---> usermod (de manera més manual al adduser). 
  
  <img width="747" height="452" alt="image" src="https://github.com/user-attachments/assets/9e859646-520c-4b77-9bf6-dfaa80875e86" />

- Comprovo que finalment hem pogut accedir graficament desde el menu de la home d'usuaris, ens apareix l'usuari vesper i, després ho comprovo amb un ls i ls vesper/
  <img width="694" height="117" alt="image" src="https://github.com/user-attachments/assets/5986b2dc-f3c0-448a-9fdc-b36b707a79e7" />

- Creem 4 usuaris i procedirem a borrar-los de dues formes. La primera:
  
<img width="501" height="120" alt="image" src="https://github.com/user-attachments/assets/4471304c-c5b5-4a86-ac06-cafc0d453dba" />

- La segona forma. Borrem amb userdel -l

- Per a bloqueijar un usuari:

-<img width="734" height="127" alt="image" src="https://github.com/user-attachments/assets/a9309458-8c74-4b6a-8cce-edc453600d17" />

- Per a desblocarlo:

<img width="944" height="99" alt="image" src="https://github.com/user-attachments/assets/aec824c3-7a26-4620-8ef3-3164fd321fc7" />

- Ara crearem un grup de usuaris:
  
<img width="929" height="239" alt="image" src="https://github.com/user-attachments/assets/dd251ea1-5f63-49cb-87be-35441e673d89" />

* 3 maneres de agregar usuaris al grup:

<img width="930" height="201" alt="image" src="https://github.com/user-attachments/assets/de36b53e-e7ee-4bc0-bfd0-2525e542b7fe" />

- ara voldrem borrar usuaris del grup:

<img width="934" height="138" alt="image" src="https://github.com/user-attachments/assets/3497738a-fd22-4362-8f8b-bf94d156f3f1" />

- Amb la comanda -g serveix per a modificar el grup principal de l'usuari. 
  
<img width="924" height="118" alt="image" src="https://github.com/user-attachments/assets/80f6a9ac-e6fe-41dc-92ca-7f884ca30506" />

- Amb això veurem a quins grups pertany l'usuari

<img width="919" height="99" alt="image" src="https://github.com/user-attachments/assets/29c6b3ea-540a-48b2-a4f1-d5146079c434" />

- Ara borrarem el grup, pero observem que tenim un grup principal, cosa que haurem de borrar que sigui el grup primari o principal i després ja podrem borrar el grup.

<img width="922" height="115" alt="image" src="https://github.com/user-attachments/assets/83b46e44-ef3f-4978-afdb-4fa6f6c9f7b3" />


- <img width="873" height="605" alt="image" src="https://github.com/user-attachments/assets/c15bb3a6-fed4-424d-83b8-66ea5708d6cd" />

- si vull modificar la commanda adduser, canviar el DHOME, per la q vulguesem això seria el nostre home per a aquest usuari i, canviar el first UID I GID que es per a canviar l'assignacio del nostre usuari

 <img width="817" height="496" alt="image" src="https://github.com/user-attachments/assets/251ac437-dd37-4179-bec7-d30267aacc37" />


 <img width="817" height="496" alt="image" src="https://github.com/user-attachments/assets/2d82c125-8ce2-49f8-a407-6a4ac3ee0e26" />



- si vull canviar caducitats de contrasenyes de adduser i useradd:
<img width="873" height="605" alt="image" src="https://github.com/user-attachments/assets/e810c3b9-c8d7-4e54-bf33-fdff13dc6837" />


- Amb axò canvio a bash
<img width="873" height="605" alt="image" src="https://github.com/user-attachments/assets/f2398664-0e72-40d1-986d-71f5aa1e28f1" />

proves de que han funcionat les modificacions anteriors amb la creació d'un usuari adduser
<img width="878" height="630" alt="image" src="https://github.com/user-attachments/assets/98dbc21e-54dc-45bf-9e46-3ecb7fe3db4a" />

- Ara comprovem useradd
  
<img width="877" height="119" alt="image" src="https://github.com/user-attachments/assets/b91d873a-1808-45c2-a5a5-532689501ff8" />


- fer ls -la i fer una prova



-------
FER AIXÓ SEGÜENT I BORRAR LO QUE PERTANY A AIXÒ DE LES PROVES ANTERIORS DE EXEMPLE, OSIGUE BORRAR LES PROVES ANTERIORS PER A POSAR EL MEU EXEMPLE.

**EXERCICI PROVA ADDUSER I USERADD EN UNA PROVA FETA PROPIA**, després d'haver creat les modificacions del usuari (REPLICANT TOT LO ANTERIOR), doncs canviar coses amb el nano.profile, nano.bashrc, nano .bash_logout i també  desde ubuntu server amb el control dret +f5, comprovar l'usuari creat nou amb la carpeta que haurie modificat com a home, si surten les modificacions del nano que acabo de nombrar.:

<img width="1035" height="760" alt="image" src="https://github.com/user-attachments/assets/311b95a5-3eb9-4540-ba12-8b52d5bdbfcd" />

- Per ultim entrarem a la carpeta Imágenes o la que haurem dit, amb cd Imágenes/, crear una carpeta buida amb touch i el nom de la carpeta, comprovar amb ls si la hem creada, fer exit de la terminal, i control dret + f2 per a sortir.
  


**3.3** Personalització de comandes
- 

# **4.** Gestió de procesos
