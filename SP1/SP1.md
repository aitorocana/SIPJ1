---
layout: default
title: "SP1 Avaluació, Instal·lació i Configuració de Xarxes i Sistemes Operatius"
---

## Virtualització i instal·lació del SO Ubuntu
## Virtualització

Per a la vitualització, primer busquem els requisits mínims que demana UBuntu a la seva documentació oficial, per tal de saber més o menys el que hem de posar:

<img width="922" height="555" alt="image" src="https://github.com/user-attachments/assets/9ebd2d0b-a558-4122-b85d-a03c8ea73f14" />

Per tant, com podem veure, ens demana segons la documentació, una RAM mínima d'uns 3GB i un almacenament mínim de 25GB per a que funcioni minimament.
Nosaltres hem escollit, tal i com podem veure en la següent captura, una RAM de 4GB i hem assignat un almacenament de 80GB.

<img width="1172" height="859" alt="image" src="https://github.com/user-attachments/assets/7fad345c-dd0d-49ef-aca7-9acbce5a4c42" />

En la següent imatge, començem a escollir la carpeta de destinatari de la nova màquina virtual, escollint el nom que es visualitzarà com a nova màquina virtual amb el seu sistema operatiu escollit. Però encara no triem la ISO. Ho farem després.
<img width="871" height="473" alt="image" src="https://github.com/user-attachments/assets/9d2321fd-699a-4430-bed2-766afc7cb368" />

En aquesta part, el que fem es triar la destinació de memòria que li volem donar per a un funcionament correcte de la nostra màquina virtual, juntament
amb quants de nuclis volem posar. Sempre seguint els requisits mínims que ens demana la documentació oficlal.
<img width="879" height="476" alt="image" src="https://github.com/user-attachments/assets/c8d9af39-81cf-4ed1-8c75-a5ce6abff082" />
<img width="879" height="476" alt="image" src="https://github.com/user-attachments/assets/3b8de964-8e64-418e-b752-0d86aad15398" />

<img width="873" height="580" alt="image" src="https://github.com/user-attachments/assets/34bb7107-b7bb-4573-80d1-669dad129bf8" />
Aqui, dintre de paràmetres del client, a emmagatzematge escollim la ISO que volem

## Instal·lació

En el moment de la instal·lació, ens demanarà l'idioma que volem escollir, després el tipus d'instal·lació que volem i el que ens interessa es l'opció de crear particions:

<img width="908" height="662" alt="image" src="https://github.com/user-attachments/assets/b2995272-1591-44da-a0cc-5d754c4e74d1" />

Aquí procedim a dividir el disc sorbe les 80GB que hem escollit en el moment de la virtualització de la màquina virtual. Però com pròximament instal·larem amb aquestes 80GB el windows,
deixem 40GB a banda, que les destinarem per a l'instal·lació del Windows i les altres 40GB per a l'Ubuntu.

<img width="1282" height="865" alt="image" src="https://github.com/user-attachments/assets/5263f550-3d31-45dc-81b7-0f030162bf60" />

El cas es que hem de pensar que sol tenim 40GB disponibles per a l'Ubuntu i per a repartir aquests per a la repartició que necessita Ubuntu per a la instal·lació. 
Primer dividirem 25 GB, per a l'arrel que es on van instal·lats els programes i el sistema.

<img width="862" height="649" alt="image" src="https://github.com/user-attachments/assets/cd540697-7714-4385-b25c-50a9d1bec1ed" />

Ara destinarem 13GB per al /home, que es on van guardats els teus fitxers.
<img width="862" height="649" alt="image" src="https://github.com/user-attachments/assets/97b35073-988e-4867-9d5b-b3936b8d86f1" />

Destinem 2GB per al /swap, que bàsicament es la memòria d'intercanvi.
<img width="862" height="649" alt="image" src="https://github.com/user-attachments/assets/713eb178-ab58-414b-a295-1555ee132615" />

Agreguem aqui 1GB per a la EFI per a guardar el sistema d'arrancada.
<img width="862" height="649" alt="image" src="https://github.com/user-attachments/assets/e9925874-f2b4-4700-9dff-8cdc2dd35f9b" />

Aqui fem l'última partició d'1GB per al BIOS boot
<img width="843" height="640" alt="image" src="https://github.com/user-attachments/assets/d3466d99-f3fe-4ba5-a556-e1fb692c969b" />














## Llicenciament






## Instal·lacions duals i gestors d'arrancada



## Particions i punts de restauració




## Configuració bàsica de la xarxa






## Comandes generals i instal·lació d'aplicacions
