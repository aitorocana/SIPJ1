
# Exercici 1. Monitorització bàsica de Windows Server

## Objectiu
Monitoritzar l’estat del servidor utilitzant eines integrades de Windows Server.

## Pas a pas

### 1. Obrir el Monitor de recursos

Al servidor, obre:

Administrador de tasques → Rendiment → Obre el Monitor de recursos

<img width="779" height="586" alt="image" src="https://github.com/user-attachments/assets/19423f45-e5cf-47e6-b377-638bf09a7bf8" />


### 2. Revisar l’ús de CPU

Comprova:

- processos que consumeixen més CPU

<img width="468" height="586" alt="image" src="https://github.com/user-attachments/assets/f74be293-2c1f-4205-b321-a2a8d438d866" />


- percentatge total d’ús

<img width="850" height="447" alt="image" src="https://github.com/user-attachments/assets/c52fb0ad-d290-4edf-9cd7-43ada80ab638" />


### 3. Revisar la memòria RAM

Accedeix a la pestanya “Memòria”.

Comprova:

- memòria utilitzada

<img width="405" height="464" alt="image" src="https://github.com/user-attachments/assets/410e2a91-a51f-4671-a6e8-da3b0f51d000" />

- memòria lliure

<img width="755" height="570" alt="image" src="https://github.com/user-attachments/assets/f895bb9c-ba90-4fa8-9e92-de1bb389b82e" />


Fes una captura.

### 4. Revisar el disc

Accedeix a “Disc”.

Comprova:

- processos amb més lectura/escriptura
- activitat del disc

<img width="871" height="572" alt="image" src="https://github.com/user-attachments/assets/8553da2f-622f-4feb-afd6-e8e9a3b2d9f2" />

- El percentatge d’activitat del disc és de 1%
- La velocitat d’escriptura és de 68,9 KB/s
- La velocitat de lectura és de 0 KB/s
- El temps de resposta és de 0,4 ms
- el disc és un HDD (SATA)
- té una capacitat aproximada de 50 GB

### 5. Revisar la xarxa

Accedeix a “Xarxa”.

Comprova:

- programes que utilitzen la xarxa
- velocitat d’enviament i recepció

<img width="1032" height="736" alt="image" src="https://github.com/user-attachments/assets/0091a83c-a462-4599-a16e-b82d9eb048ed" />

<img width="786" height="184" alt="image" src="https://github.com/user-attachments/assets/d6bd7d72-b7ee-4b24-a017-7dd7614e6fa0" />

### 6. Revisar els esdeveniments del sistema

Obre:

Administrador del servidor → Eines → Visor d’esdeveniments

Consulta:

- Errors del sistema
- Advertiments
- Errors d’aplicació

<img width="1025" height="738" alt="image" src="https://github.com/user-attachments/assets/88aa8708-27b7-4d93-ae0a-dd2319d255cd" />

<img width="1025" height="738" alt="image" src="https://github.com/user-attachments/assets/e438d2eb-337a-471b-987e-d7c9cd1e13b9" />

<img width="1025" height="738" alt="image" src="https://github.com/user-attachments/assets/87049014-b491-40a8-8373-6699c93b53af" />


---


# Exercici 3. Consulta de llicències de Windows Server i equips units al domini

## Enunciat

Una empresa disposa de:

- 1 servidor Windows Server
- 25 ordinadors
- 10 portàtils
- 32 usuaris
- tots els equips units al domini

L’empresa necessita calcular el cost aproximat de les llicències necessàries per al servidor i per als equips o usuaris que accedeixen al domini.

## Tasques

### 1. Busca el preu aproximat de:

- Windows Server Standard

<img width="1701" height="701" alt="image" src="https://github.com/user-attachments/assets/79573d02-0d23-4b21-914e-416731d29b8b" />

- Windows Server Datacenter

<img width="1701" height="701" alt="image" src="https://github.com/user-attachments/assets/f4495d56-024a-47e7-afa3-31631aac350b" />

- User CAL

<img width="1701" height="701" alt="image" src="https://github.com/user-attachments/assets/faa90ff9-b8cf-4ea2-9302-a87403670eb0" />

- Device CAL

<img width="1701" height="701" alt="image" src="https://github.com/user-attachments/assets/23a8c486-dc5e-4366-9b6a-f64bc89b33af" />

### 2. Explica:

- què és una CAL

Amb la User CAL, es compra una llicència per a cada usuari que accedeix al servidor per utilitzar serveis com l’emmagatzematge de fitxers o la impressió, independentment del nombre de dispositius que utilitzi per accedir-hi.

Comprar una User CAL pot ser l’opció més convenient si els treballadors de l’empresa necessiten accedir a la xarxa corporativa des de diversos dispositius o des de dispositius diferents, o simplement si a l’organització hi ha més dispositius que usuaris.

- diferència entre User CAL i Device CAL

Amb una Device CAL, es compra una llicència per a cada dispositiu que accedeix al servidor, independentment del nombre d’usuaris que utilitzin aquest dispositiu per accedir-hi.

Les Device CAL són més adequades des del punt de vista administratiu i econòmic quan l’empresa té treballadors que comparteixen dispositius, per exemple en diferents torns de treball.

### 3. Calcula:

- cost aproximat amb User CAL

<img width="1701" height="701" alt="image" src="https://github.com/user-attachments/assets/b38942a7-f03e-48cb-896d-ec843486a028" />

si 5 user CAL hem costa 1.406 € i el servidor standard 849,99 € ---> per a 32 usuaris de l'empresa i tinc 5 cal llavors 32/5 = 6,4
- llavors calen calen 7 paquets de 5 User CAL. ----> 7×1406=9842

Cost CAL:

9.842 €

Cost total:
9842+849.99=10691.99 amb el servidor inclos


- cost aproximat amb Device CAL
- L’empresa té: 25 ordinadors 10 portàtils Total: 25+10=35, llavors es necessiten 35 Device CAL. Com que el pack és de 5 CAL: 35÷5=7, calen 7 paquets de 5 Device CAL.

COST DEVICE CAL:

9842€

Cost total:
9842+849.99=10691.99 amb el servidor inclos


### 4. Indica quin model és més adequat per a aquesta empresa i justifica la resposta.
El model més adequat és User CAL. Tot i que el cost és pràcticament igual
- els usuaris poden accedir des de diversos dispositius
- és més flexible per a portàtils i teletreball
- facilita l’administració dels accessos

Per això, l’opció recomanada és:

Windows Server Standard
32 User CAL

### 5. Mostra els equips del domini des de:

- Active Directory
- PowerShell


