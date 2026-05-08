# Fase 1 – Preparació del sistema

## Pas 1. Afegir un nou disc virtual a la màquina virtual

## Pas 2. Iniciar Windows i obrir Gestió de discs

## Pas 3. Inicialitzar el disc i crear dues particions
- Una anomenada `Dades`
- Una en FAT32 anomenada `Portable`

## Pas 4. Assignar lletres i comprovar amb `diskpart` la configuració

---

# Fase 2 – Quotes i usuaris

## Pas 5. Activar quotes de disc a la partició `Dades` (NTFS)

## Pas 6. Establir límit de 300 MB per usuari amb notificació d’advertència

## Pas 7. Crear dos usuaris locals
- `alumne1`
- `alumne2`

## Pas 8. Afegir-los a un grup nou anomenat `Limitats`

## Pas 9. Provar la còpia de fitxers dins `Dades` per veure com actuen les quotes (superar límit)

---

# Fase 3 – Script de còpia i automatització

## Pas 10. Afegir un tercer disc virtual i formatar-lo en NTFS com a `Backups`

## Pas 11. Crear la carpeta `CòpiesUsuaris` dins `Backups`

## Pas 12. Crear un script `.bat`

Ha de copiar:

```bat
C:\Users\%USERNAME%
```

a:

```bat
E:\CòpiesUsuaris\%USERNAME%
```

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
