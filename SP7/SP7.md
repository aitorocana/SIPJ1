
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
- memòria lliure

Fes una captura.

### 4. Revisar el disc

Accedeix a “Disc”.

Comprova:

- processos amb més lectura/escriptura
- activitat del disc

### 5. Revisar la xarxa

Accedeix a “Xarxa”.

Comprova:

- programes que utilitzen la xarxa
- velocitat d’enviament i recepció

### 6. Revisar els esdeveniments del sistema

Obre:

Administrador del servidor → Eines → Visor d’esdeveniments

Consulta:

- Errors del sistema
- Advertiments
- Errors d’aplicació

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
- Windows Server Datacenter
- User CAL
- Device CAL

### 2. Explica:

- què és una CAL
- diferència entre User CAL i Device CAL

### 3. Calcula:

- cost aproximat amb User CAL
- cost aproximat amb Device CAL

### 4. Indica quin model és més adequat per a aquesta empresa i justifica la resposta.

### 5. Mostra els equips del domini des de:

- Active Directory
- PowerShell
