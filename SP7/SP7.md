
# Exercici 1. Monitorització bàsica de Windows Server

## Objectiu
Monitoritzar l’estat del servidor utilitzant eines integrades de Windows Server.

## Pas a pas

### 1. Obrir el Monitor de recursos

Al servidor, obre:

Administrador de tasques → Rendiment → Obre el Monitor de recursos

### 2. Revisar l’ús de CPU

Comprova:

- processos que consumeixen més CPU
- percentatge total d’ús

Fes una captura.

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

# Exercici 2. Connexió remota a Windows Server

## Objectiu
Configurar i utilitzar l’Escriptori remot per connectar-se a un Windows Server des d’un altre equip.

## Part 1. Configuració del servidor

### 1. Obrir la configuració d’Escriptori remot

Al servidor:

Inici → Configuració → Sistema → Escriptori remot

### 2. Activar l’Escriptori remot

Activa:

Habilitar Escriptori remot

Prem:

Confirmar

### 3. Permetre usuaris remots

A la mateixa finestra, prem:

Selecciona els usuaris que poden accedir remotament

Prem:

Afegir

Escriu el nom de l’usuari que podrà connectar-se.

Prem:

Comprova els noms

Si l’usuari existeix correctament, prem:

Acceptar

### 4. Comprovar el nom del servidor

Obre el símbol del sistema:

```bash
hostname
```

Anota el nom del servidor.

### 5. Comprovar la direcció IP del servidor

Al símbol del sistema executa:

```bash
ipconfig
```

Busca:

Adreça IPv4

Anota la direcció IP.

### 6. Comprovar el Firewall

Obre:

Panell de control → Sistema i seguretat → Firewall de Windows Defender

Prem:

Permetre una aplicació o característica a través del Firewall

Comprova que:

Escriptori remot està permès.

## Part 2. Connexió des del client

### 7. Obrir Connexió a Escriptori remot

Al client:

Win + R

Escriu:

```text
mstsc
```

Prem Enter.

### 8. Escriure el nom o la IP del servidor

Introdueix:

- el nom del servidor

o

- la direcció IP del servidor

Prem:

Connecta

### 9. Introduir les credencials

Escriu:

- nom d’usuari
- contrasenya

Prem:

Acceptar

### 10. Acceptar l’avís de connexió

Si apareix un avís de seguretat:

- marca l’opció per no tornar a mostrar-lo
- prem “Sí”

### 11. Verificar la connexió

Comprova que:

- apareix l’escriptori del servidor
- pots obrir carpetes
- pots obrir l’Administrador del servidor

Fes una captura de pantalla.

## Part 3. Tancar la sessió

### 12. Tancar la connexió remota

Al servidor remot:

Inici → Tanca sessió

No apagar el servidor.

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
