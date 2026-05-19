
# Exercici 1. Monitorització bàsica de Windows Server

## Objectiu
Monitoritzar l’estat del servidor utilitzant eines integrades de Windows Server.

## Pas a pas

### 1. Obrir el Monitor de recursos

Al servidor, obre:

Administrador de tasques → Rendiment → Obre el Monitor de recursos

<img width="779" height="586" alt="image" src="https://github.com/user-attachments/assets/19423f45-e5cf-47e6-b377-638bf09a7bf8" />

<img width="945" height="722" alt="image" src="https://github.com/user-attachments/assets/46859c8c-c1cb-4929-9ca7-0b6aa87c094c" />



### 2. Revisar l’ús de CPU

Comprova:

- processos que consumeixen més CPU

<img width="468" height="586" alt="image" src="https://github.com/user-attachments/assets/f74be293-2c1f-4205-b321-a2a8d438d866" />

<img width="728" height="388" alt="image" src="https://github.com/user-attachments/assets/e2d2169a-5067-4cfc-9365-4a57121bae48" />


### 3. Revisar la memòria RAM

Accedeix a la pestanya “Memòria”.

Comprova:

- memòria utilitzada


<img width="891" height="602" alt="image" src="https://github.com/user-attachments/assets/e16f510f-574a-44d0-833b-b5557461b5a0" />


- memòria lliure

<img width="831" height="281" alt="image" src="https://github.com/user-attachments/assets/e36dca83-9cec-4948-a878-94c177cf1a28" />


Fes una captura.

### 4. Revisar el disc

Accedeix a “Disc”.

Comprova:

- processos amb més lectura/escriptura
- activitat del disc

<img width="861" height="473" alt="image" src="https://github.com/user-attachments/assets/b8bd312a-ed9c-480f-ba68-799f897fe618" />


### 5. Revisar la xarxa

Accedeix a “Xarxa”.

Comprova:

- programes que utilitzen la xarxa
- velocitat d’enviament i recepció

<img width="1032" height="736" alt="image" src="https://github.com/user-attachments/assets/0091a83c-a462-4599-a16e-b82d9eb048ed" />

<img width="861" height="473" alt="image" src="https://github.com/user-attachments/assets/ae97ed83-6037-443b-b0c4-f9de88af213d" />

<img width="861" height="473" alt="image" src="https://github.com/user-attachments/assets/98861787-1eea-455d-ba83-4343a241a652" />


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


