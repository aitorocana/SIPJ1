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

<img width="682" height="174" alt="image" src="https://github.com/user-attachments/assets/07bd438b-a086-4cd2-8109-ac338d41e229" />







  
* ### Comandes

  
<img width="807" height="534" alt="image" src="https://github.com/user-attachments/assets/843977b2-0dcf-4ebb-939e-66367e32c272" />

COmprovem el disk que hem posat de 10GB

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
# **4.** Gestió de procesos
