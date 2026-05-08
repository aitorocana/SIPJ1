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


<img width="829" height="508" alt="image" src="https://github.com/user-attachments/assets/254378d3-4cc9-4316-b215-c251459fbe3c" />

## Pas 13. Obrir `gpedit.msc`

Ruta:

```text
Configuració d’usuari → Scripts → Inici de sessió
```

## Pas 14. Assignar l’script perquè s’executi automàticament quan `alumne1` o `alumne2` inicien sessió

---

# Fase 4 – Verificació i documentació

## Pas 15. Iniciar sessió amb `alumne1`

Comprovar:
- Que l’script fa la còpia a `Backups`
- Que la quota de `Dades` bloqueja si supera el límit
- Que tota la configuració funciona correctament

---

# Fase 5 – Gestió de processos i serveis

## Pas 19. Llistar processos actius

- Inicia sessió com `alumne1`
- Obre la consola (`cmd`) com a usuari
- Executa:

```cmd
tasklist
```

- Copia el resultat a un fitxer:

```cmd
tasklist > C:\Users\%USERNAME%\processos_inici.txt
```

- Observa processos típics:
  - `explorer.exe`
  - `SearchIndexer.exe`
  - `OneDrive.exe`
  - etc.

## Pas 20. Identificar processos prescindibles

Busca processos no essencials per a l’usuari:
- `OneDrive.exe`
- `Teams.exe`
- `SkypeApp.exe`

Fes una taula amb:
- Nom del procés
- Memòria usada
- Justificació per eliminar-lo

## Pas 21. Eliminar processos manualment

Executa:

```cmd
taskkill /IM OneDrive.exe /F
```

Comprova amb:

```cmd
tasklist
```

Fes una captura abans i després.

## Pas 22. Automatitzar-ho a l’inici de sessió

Modifica l’script d’inici de sessió afegint:

```bat
taskkill /IM OneDrive.exe /F
taskkill /IM Teams.exe /F
```

Reengega sessió com `alumne2` i comprova que aquests processos no es llencen o es tanquen.

## Pas 23. Documentació

- Afegeix el fitxer de `tasklist` i la taula justificativa a la documentació amb MkDocs
- Explica què passa si mates un procés crític com `explorer.exe` (prova controlada)
- Comenta com aquesta gestió pot millorar el rendiment de màquines virtuals o equips amb pocs recursos

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
- Crea la carpeta:

```text
D:\Projectes
```

---

## Pas 25. Assignar permisos normals al grup

1. A les propietats de la carpeta `D:\Projectes`, ves a la pestanya **Seguretat**
2. Fes clic a **Avançat**
3. Desactiva la herència i conserva els permisos existents
4. Elimina `Users` o `Everyone` si hi apareixen
5. Afegeix el grup `Limitats` i dona-li **Control total**
6. Aplica els canvis

Ara qualsevol usuari del grup `Limitats` té accés complet.

---

## Pas 26. Comprovar accés amb `alumne1`

1. Inicia sessió com `alumne1`
2. Crea un fitxer dins `D:\Projectes`
3. Modifica’l i elimina’l

Tot hauria de funcionar correctament perquè hereta permisos del grup `Limitats`.

---

## Pas 27. Aplicar excepció per `alumne2`

Torna a iniciar sessió com administrador i executa:

```cmd
icacls "D:\Projectes" /grant:r alumne2:(R)
```

Això substitueix qualsevol permís anterior d’`alumne2` i li dona només lectura.

---

## Pas 28. Comprovar l’excepció amb `alumne2`

1. Inicia sessió com `alumne2`
2. Intenta obrir un fitxer dins `D:\Projectes` → ha de poder llegir-lo
3. Intenta editar-lo o crear-ne un de nou → ha de rebre un missatge de denegació

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

Això confirma que:
- El grup `Limitats` té control total
- `alumne2` té només permisos de lectura
