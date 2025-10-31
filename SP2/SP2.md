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



## **1.6.** TIpus de formateig
## **1.7.** Particions/volums
* ### GPARTED
* ### Comandes




# **2.** Còpies de seguretat i automatització de tasques**1.**
# **3.** Gestió d'usuaris, grups i permisos
# **4.** Gestió de procesos
