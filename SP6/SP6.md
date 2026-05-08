# Fase 1 – Preparació del sistema

## Pas 1. Afegir un nou disc virtual a la màquina virtual

- Primer anar a configuració i emmagatzemtage

<img width="918" height="582" alt="image" src="https://github.com/user-attachments/assets/8f107533-9f16-4e57-83ca-a26de44ab08f" />

- Afegir nou disc dur
  
<img width="918" height="582" alt="image" src="https://github.com/user-attachments/assets/c70d958a-39cc-4a89-a135-81ef49aae981" />

<img width="918" height="582" alt="image" src="https://github.com/user-attachments/assets/c69aa9af-4576-4f8e-b6a5-ee0f9b096f0d" />

<img width="918" height="582" alt="image" src="https://github.com/user-attachments/assets/b820a90d-ade7-4bfd-8e6c-796c5498ba7b" />

<img width="841" height="524" alt="image" src="https://github.com/user-attachments/assets/705d7a10-2168-403d-b6b8-f1b5c0bc0be2" />

## Pas 2. Iniciar Windows i obrir Gestió de discs

<img width="823" height="576" alt="image" src="https://github.com/user-attachments/assets/b66b4b5a-05d6-4205-a20b-064bf6c5815a" />


## Pas 3. Inicialitzar el disc i crear dues particions


- Una anomenada `Dades`
  
-Click dret i cickar nuevo volumen simple

<img width="823" height="576" alt="image" src="https://github.com/user-attachments/assets/716f1922-68e9-4382-9200-dae15912e53c" />

-Assignar el espai i assignar la lletra del disc

<img width="823" height="576" alt="image" src="https://github.com/user-attachments/assets/0c9fee0c-670a-430b-aa9c-69e20f1058a1" />

<img width="823" height="576" alt="image" src="https://github.com/user-attachments/assets/8aaac76e-c113-47ae-a044-ac8adc6a4cd9" />

<img width="823" height="576" alt="image" src="https://github.com/user-attachments/assets/c10373be-b3a5-4e45-ba0f-aed126eaa7bf" />

- Resultat

<img width="823" height="576" alt="image" src="https://github.com/user-attachments/assets/606c0f45-b457-4d7e-a3a1-f0ac64ae36e6" />

- Una en FAT32 anomenada `Portable`

<img width="812" height="158" alt="image" src="https://github.com/user-attachments/assets/816e79c0-08d3-42dc-80c4-81a99e378a28" />

- Assigno l'espai que queda i assigno lletra al disc

<img width="812" height="454" alt="image" src="https://github.com/user-attachments/assets/19616554-5f88-4934-b99e-d6be9681494d" />

<img width="812" height="454" alt="image" src="https://github.com/user-attachments/assets/5c189d64-06b1-4f9c-b14b-0a9e507444ba" />

<img width="812" height="454" alt="image" src="https://github.com/user-attachments/assets/5f07eae1-561d-4281-a8c9-2cbaca711cb8" />


## Pas 4. comprovar amb `diskpart` la configuració

- Obrir cmd amb el WIndows + r i posar diskpart i seguit list disk i list volume

<img width="827" height="512" alt="image" src="https://github.com/user-attachments/assets/31f0c53c-2dd8-4805-840e-c60994438e1c" />







---

# Fase 2 – Quotes i usuaris

## Pas 5. Activar quotes de disc a la partició `Dades` (NTFS)

- obrir primer este equipo

<img width="858" height="591" alt="image" src="https://github.com/user-attachments/assets/c0e16724-2684-4097-b774-812d169db6f0" />

- Anar a propiedades de la partició Dades i cuota:

<img width="858" height="591" alt="image" src="https://github.com/user-attachments/assets/ab2e905e-d34d-499e-b0a3-14e2ec1b9d3d" />

- activar les dos primeres caselles

<img width="368" height="461" alt="image" src="https://github.com/user-attachments/assets/ede061b4-3c20-4a5a-9bb5-b104e6a2e17a" />

## Pas 6. Establir límit de 300 MB per usuari amb notificació d’advertència

<img width="368" height="461" alt="image" src="https://github.com/user-attachments/assets/f848a672-0645-483e-96ea-6e67231a1743" />


## Pas 7. Crear dos usuaris locals
- `alumne1`
- `alumne2`

<img width="699" height="461" alt="image" src="https://github.com/user-attachments/assets/8e546ad5-6469-41c6-8a35-946ff021017c" />

## Pas 8. Afegir-los a un grup nou anomenat `Limitats`

<img width="699" height="461" alt="image" src="https://github.com/user-attachments/assets/85e86647-9837-4726-9e19-f1e4fce3fcd7" />


## Pas 9. Provar la còpia de fitxers dins `Dades` per veure com actuen les quotes (superar límit)

---

# Fase 3 – Script de còpia i automatització

## Pas 10. Afegir un tercer disc virtual i formatar-lo en NTFS com a `Backups`

<img width="829" height="508" alt="image" src="https://github.com/user-attachments/assets/4e268041-9020-45ff-a5ce-36a65bd080c2" />

<img width="829" height="508" alt="image" src="https://github.com/user-attachments/assets/c353d38e-cc34-44ca-8fc4-4e0dbff840d1" />




## Pas 11. Crear la carpeta `CòpiesUsuaris` dins `Backups`

<img width="829" height="508" alt="image" src="https://github.com/user-attachments/assets/1990e772-7430-4572-9621-984e1e0f45bc" />




## Pas 12. Crear un script `.bat`

Ha de copiar:

```bat
C:\Users\%USERNAME%
```

a:

```bat
E:\CòpiesUsuaris\%USERNAME%
```

<img width="829" height="508" alt="image" src="https://github.com/user-attachments/assets/b91414c5-0ae7-486f-8ee9-ef7c92d77a3e" />

<img width="829" height="508" alt="image" src="https://github.com/user-attachments/assets/254378d3-4cc9-4316-b215-c251459fbe3c" />

## Pas 13. Obrir `gpedit.msc`

Ruta:

```text
Configuració d’usuari → Scripts → Inici de sessió
```

<img width="829" height="508" alt="image" src="https://github.com/user-attachments/assets/74163ad8-2eb9-49dd-b47c-f7eb3a97c3cf" />


## Pas 14. Assignar l’script perquè s’executi automàticament quan `alumne1` o `alumne2` inicien sessió

<img width="829" height="508" alt="image" src="https://github.com/user-attachments/assets/eaec1cc7-3918-4eb2-a0e7-0aab8cdf78e1" />


---

# Fase 4 – Verificació i documentació

## Pas 15. Iniciar sessió amb `alumne1`

Comprovar:
- Que l’script fa la còpia a `Backups`

---

<img width="708" height="552" alt="image" src="https://github.com/user-attachments/assets/9b052794-35f6-4154-a951-5f6c8f34a149" />

<img width="708" height="552" alt="image" src="https://github.com/user-attachments/assets/df089642-5e13-4dd9-9ea5-739915c2b07d" />


# Fase 5 – Gestió de processos i serveis

## Pas 19. Llistar processos actius

- Inicia sessió com `alumne1`

<img width="702" height="94" alt="image" src="https://github.com/user-attachments/assets/c68a3cc7-ac53-41fc-b938-e1cdeebe2186" />

- Obre la consola (`cmd`) com a usuari

<img width="836" height="341" alt="image" src="https://github.com/user-attachments/assets/333ff3b6-9614-4671-9a54-fcecc2e94af6" />

- Executa:

```cmd
tasklist
```

<img width="844" height="631" alt="image" src="https://github.com/user-attachments/assets/bd9976c7-17f2-4fe1-a395-08277e817a98" />


- Copia el resultat a un fitxer:

```cmd
tasklist > C:\Users\%USERNAME%\processos_inici.txt
```
<img width="747" height="71" alt="image" src="https://github.com/user-attachments/assets/f1feda57-a747-4c25-b2ec-6f217c57647f" />


- Observa processos típics:
  - `explorer.exe`
  - `SearchIndexer.exe`
  - `OneDrive.exe`
  - etc.
 
<img width="924" height="552" alt="image" src="https://github.com/user-attachments/assets/82dfe2f5-0f78-4169-9189-eb767f7e32e8" />

<img width="881" height="556" alt="image" src="https://github.com/user-attachments/assets/9e508740-8a14-4351-8faa-fc0839d589fe" />

<img width="850" height="132" alt="image" src="https://github.com/user-attachments/assets/481cd798-3c41-4f8f-ba83-95b9aaab43b7" />


## Pas 20. Identificar processos prescindibles

Busca processos no essencials per a l’usuari:
- `OneDrive.exe`

<img width="850" height="132" alt="image" src="https://github.com/user-attachments/assets/481cd798-3c41-4f8f-ba83-95b9aaab43b7" />


Fes una taula amb:
- Nom del procés
- Memòria usada
- Justificació per eliminar-lo

| Procés | Memòria usada | Justificació |
|---|---|---|
| OneDrive.exe | 136.416 KB | Procés de sincronització al núvol no necessari. Consumeix memòria RAM i recursos en segon pla. |

## Pas 21. Eliminar processos manualment

Executa:

```cmd
taskkill /IM OneDrive.exe /F
```
<img width="866" height="142" alt="image" src="https://github.com/user-attachments/assets/58d9f352-e3f1-49a1-b149-8659ab6bfb76" />

<img width="866" height="142" alt="image" src="https://github.com/user-attachments/assets/b178f6f8-efa3-4625-b7df-1ec13f16bf0d" />

- Tindria que apareixer dalt de OneDrive.sync.exe

<img width="889" height="690" alt="image" src="https://github.com/user-attachments/assets/9813c127-c1fb-4b57-98e9-42aa6c6ee44f" />


## Pas 22. Automatitzar-ho a l’inici de sessió

Modifica l’script d’inici de sessió afegint:

```bat
taskkill /IM OneDrive.exe /F
taskkill /IM Teams.exe /F
```

<img width="889" height="690" alt="image" src="https://github.com/user-attachments/assets/fc66a1c6-db7a-4ace-93df-506487d5908c" />


Reengega sessió com `alumne2` i comprova que aquests processos no es llencen o es tanquen.

<img width="813" height="111" alt="image" src="https://github.com/user-attachments/assets/11c3ba86-c066-48e4-9e65-d7e4d22b1a71" />

<img width="754" height="405" alt="image" src="https://github.com/user-attachments/assets/e76fab50-8e1c-404e-b573-3cf4f36234cd" />

<img width="799" height="641" alt="image" src="https://github.com/user-attachments/assets/b04bf613-b18d-4b24-8568-16a7b1d822bb" />

## Pas 23. Documentació

- Afegeix el fitxer de `tasklist` i la taula justificativa a la documentació amb MkDocs
- Explica què passa si mates un procés crític com `explorer.exe` (prova controlada)
- Comenta com aquesta gestió pot millorar el rendiment de màquines virtuals o equips amb pocs recursos

Si mato el proces explorer.exe, el que fa es que com es l'encarregat de tota la interficie gràfica, com la barra de tareas, explorador, tot el que veus al escriptori, carpetes, el que fas es temporalment es apagar aquesta interficie, però funcionarà tot igual ja que el SO, funcionaria en segon pla

<img width="997" height="725" alt="image" src="https://github.com/user-attachments/assets/94a83da2-92c6-4545-bccf-ec564224b21f" />

per a recuperar la interficie, solament haurem d'iniciar el procés de nou:

<img width="1021" height="184" alt="image" src="https://github.com/user-attachments/assets/066cf595-3a79-42e6-b106-f8a53e846860" />

---

# Fase 6 – Gestió de permisos (ACLs)

## Què són les ACLs i com funcionen a Windows

A Windows, cada fitxer i carpeta té una llista de control d'accés (**ACL**, *Access Control List*).

Aquesta llista defineix qui pot fer què amb aquell recurs.

Cada entrada d'una ACL es diu **ACE** (*Access Control Entry*) i indica:
- Quina identitat (usuari o grup) està afectada
- Quins permisos té:
  - lectura
  - escriptura
  - execució
  - control total
  - etc.

Els permisos ACL són molt més detallats que els permisos normals de compartició en xarxa perquè:
- Permeten configurar permisos per fitxer o carpeta específica
- S'apliquen tant a usuaris com a grups
- Permeten combinacions com:
  - només lectura
  - només esborrar
  - control total excepte canviar permisos
- Poden ser heretats d’una carpeta superior o assignats manualment

> Exemple: una carpeta pot tenir permisos diferents per a `alumne1` i `alumne2`, tot i formar part del mateix grup.

L’objectiu és controlar qui pot accedir i modificar la carpeta `Projectes`, creada dins la partició `Dades`.

El grup `Limitats` tindrà accés total, però `alumne2` tindrà només lectura, tot i formar part del grup.

---



## Pas 24. Crear la carpeta

- Inicia sessió com a administrador
- 
<img width="1008" height="772" alt="image" src="https://github.com/user-attachments/assets/55c93432-f907-40a6-9e7a-6c8b0f2105f5" />

- Crea la carpeta:

```text
D:\Projectes
```

---

<img width="1008" height="772" alt="image" src="https://github.com/user-attachments/assets/78591f9e-b559-49cc-884b-ddc4409687a8" />


## Pas 25. Assignar permisos normals al grup

1. A les propietats de la carpeta `D:\Projectes`, ves a la pestanya **Seguretat**

<img width="1008" height="772" alt="image" src="https://github.com/user-attachments/assets/56042f72-aff0-4b43-a958-c196b60e7392" />

2. Fes clic a **Avançat**

<img width="1008" height="772" alt="image" src="https://github.com/user-attachments/assets/ecedb211-dc93-40bb-b94a-e0d4febbafbd" />

3. Desactiva la herència i conserva els permisos existents

<img width="858" height="376" alt="image" src="https://github.com/user-attachments/assets/c1e4a2cf-04e9-4505-a57b-f7cb57e457c8" />

4. Elimina `Users` o `Everyone` si hi apareixen

<img width="858" height="376" alt="image" src="https://github.com/user-attachments/assets/c908e426-5e27-43c0-88af-ca5fea13eb09" />

6. Afegeix el grup `Limitats` i dona-li **Control total**

<img width="884" height="437" alt="image" src="https://github.com/user-attachments/assets/ebd6b4ae-dccb-45d1-961d-e5cc71d8a8fc" />

7. Aplica els canvis

<img width="890" height="386" alt="image" src="https://github.com/user-attachments/assets/3e30057c-9d5c-41a2-a384-e74056c1e323" />

Ara qualsevol usuari del grup `Limitats` té accés complet.

---

## Pas 26. Comprovar accés amb `alumne1`

1. Inicia sessió com `alumne1`

<img width="922" height="605" alt="image" src="https://github.com/user-attachments/assets/35ea978e-d585-4686-b507-d7b9dae1b18d" />

2. Crea un fitxer dins `D:\Projectes`

<img width="922" height="605" alt="image" src="https://github.com/user-attachments/assets/b5aaf493-0828-4f70-899e-371270e4fa1c" />

3. Modifica’l i elimina’l

<img width="922" height="605" alt="image" src="https://github.com/user-attachments/assets/d8c1e995-6d48-46cd-ad2e-da6c0034f913" />

- Eliminar:

<img width="922" height="605" alt="image" src="https://github.com/user-attachments/assets/653abd41-a14c-401f-82f4-c3b14757b466" />



Tot hauria de funcionar correctament perquè hereta permisos del grup `Limitats`.

---

## Pas 27. Aplicar excepció per `alumne2`

Torna a iniciar sessió com administrador i executa:

<img width="922" height="605" alt="image" src="https://github.com/user-attachments/assets/f19e7c31-490b-4e06-96f7-26a30513c262" />


```cmd
icacls "D:\Projectes" /grant:r alumne2:(R)
```

<img width="922" height="605" alt="image" src="https://github.com/user-attachments/assets/f710fd8f-8320-4604-a7a7-fdf8471cac1a" />

Això substitueix qualsevol permís anterior d’`alumne2` i li dona només lectura.

---

## Pas 28. Comprovar l’excepció amb `alumne2`

1. Inicia sessió com `alumne2`

<img width="898" height="715" alt="image" src="https://github.com/user-attachments/assets/2f06537f-755b-43c4-a370-01070800aa73" />


2. Intenta obrir un fitxer dins `D:\Projectes` → ha de poder llegir-lo

<img width="898" height="715" alt="image" src="https://github.com/user-attachments/assets/663a6283-f5d7-4413-a414-c7c5d388e45a" />


3. Intenta editar-lo o crear-ne un de nou → ha de rebre un missatge de denegació

<img width="898" height="715" alt="image" src="https://github.com/user-attachments/assets/293db8ac-62aa-4771-817d-1dbcd6477e08" />


---

## Pas 29. Consultar els permisos aplicats

Obre la consola com administrador i executa:

```cmd
icacls "D:\Projectes"
```

Exemple de resultat:

```text
D:\Projectes
Limitats:(OI)(CI)(F)
alumne2:(R)
```
<img width="368" height="25" alt="image" src="https://github.com/user-attachments/assets/5444fad6-b03c-4f10-8cb5-eedb76bbc24f" />


<img width="622" height="140" alt="image" src="https://github.com/user-attachments/assets/2a2d771e-6ea3-4bf5-b01c-1a5db2489cb5" />


Això confirma que:
- El grup `Limitats` té control total
- `alumne2` té només permisos de lectura
