
# GUIA PRÀCTICA
## Instal·lació i configuració de Windows

---

# Fase 1 – Instal·lació del sistema operatiu

1. Crear màquina virtual amb VirtualBox  
2. Assignar recursos (RAM mínim 4 GB, disc mínim 40 GB)  
3. Carregar ISO de Windows 10 o Windows 11  
4. Instal·lar el sistema (idioma, usuari, contrasenya)  
5. Comprovar que arrenca correctament

<img width="909" height="846" alt="image" src="https://github.com/user-attachments/assets/ff39ae61-38f0-4b55-aaef-9f43503956d4" />
<img width="1033" height="938" alt="image" src="https://github.com/user-attachments/assets/6df8774c-acee-47d2-b403-2e9958277c7b" />

- CMD: winver-->

<img width="1030" height="849" alt="image" src="https://github.com/user-attachments/assets/7287198d-f6c0-4a8c-865e-1e3ac998a61a" />

---

# Fase 2 – Punts de restauració

6. Cercar "Crear un punt de restauració"

<img width="1013" height="849" alt="image" src="https://github.com/user-attachments/assets/cbdf62cf-e2a6-4dc8-8d98-f2d0387323c9" />

7. Activar protecció del sistema al disc C:

<img width="541" height="525" alt="image" src="https://github.com/user-attachments/assets/2c6842f9-717f-4f7f-90e6-821663aceb5c" />

<img width="541" height="525" alt="image" src="https://github.com/user-attachments/assets/364d31b6-3623-4c0b-ab9b-3828d5321f82" />

8. Crear un punt manual

<img width="497" height="488" alt="image" src="https://github.com/user-attachments/assets/e5b902b5-d321-46e4-8587-b6d6e95bfe19" />

<img width="497" height="488" alt="image" src="https://github.com/user-attachments/assets/cd60493e-d609-4946-9bcb-16e47d449be9" />

9. Fer un canvi (instal·lar app o configuració)

<img width="774" height="561" alt="image" src="https://github.com/user-attachments/assets/133a916a-1f3e-46ad-866d-87e8078b34f0" />

10. Restaurar i comprovar

<img width="410" height="206" alt="image" src="https://github.com/user-attachments/assets/804f1072-629c-4e5c-ac11-7dee2e1629b1" />

<img width="594" height="231" alt="image" src="https://github.com/user-attachments/assets/164056a0-6f67-4a38-8032-be7ef3a15829" />

<img width="594" height="231" alt="image" src="https://github.com/user-attachments/assets/5ae0299b-2332-4f5f-83da-74e8521d360f" />

<img width="935" height="776" alt="image" src="https://github.com/user-attachments/assets/289b8335-00b8-48c3-b230-2876b17a2b3d" />



---

# Fase 3 – Llicències de Windows

11. Obrir Configuració → Sistema → Activació  
12. Veure si Windows està activat  
13. Executar al cmd: `slmgr /xpr`  
14. Esbrinar llicenciament Windows i explicar breument  
15. Consultar preu aproximat d'una llicència Windows (web oficial o botigues)  

---

# Fase 4 – Gestor d'arrencada

16. Obrir Command Prompt com administrador  
17. Executar `bcdedit`  
18. Identificar els blocs:
   - Administrador de arranque de Windows (Boot Manager)
   - Cargador de arranque de Windows (Boot Loader)

19. Interpretar dades concretes

## Del bloc Boot Manager, identificar:

- `default {current}` → sistema que arrenca per defecte  
- `timeout 30` → temps d'espera abans d'arrencar  

## Del bloc Boot Loader, identificar:

- `device partition=C:` → on està instal·lat Windows  
- `path \Windows\system32\winload.efi` → fitxer que carrega el sistema  
- `description Windows 11` → sistema operatiu  

20. Respondre preguntes curtes:
   - Quin sistema s'està arrencant
   - A quin disc o partició està instal·lat
   - Quant temps espera abans d'arrencar
   - Quin fitxer inicia Windows

21. Interpretació final. *Explicar amb una frase:*
   - Qui decideix l'arrencada (Boot Manager)
   - Qui carrega el sistema (Boot Loader)

---

# Fase 5 – Xarxa bàsica

22. Obrir configuració de xarxa  
23. Consultar IP amb: `ipconfig`  
24. Configurar IP dinàmica (DHCP automàtic)  
25. Configurar IP fixa (manual: IP, màscara, gateway, DNS)  
26. Comprovar connexió amb: `ping google.com`  

---

# Fase 6 – Comandes generals

27. Obrir PowerShell  
28. Diferenciar cmd i PowerShell:
   - `cmd` → comandes bàsiques i clàssiques
   - `PowerShell` → més potent, permet treballar amb objectes i automatitzar tasques

29. Comandes bàsiques (provar-les):
   - `dir` → veure fitxers
   - `cd` → moure's per carpetes
   - `mkdir prova` → crear carpeta
   - `echo hola > fitxer.txt` → crear fitxer
   - `del fitxer.txt` → eliminar fitxer

30. Comandes útils del sistema:
   - `tasklist` → veure processos actius
   - `taskkill /IM notepad.exe /F` → tancar un procés
   - `systeminfo` → informació completa del sistema
   - `hostname` → nom de l'equip
   - `whoami` → usuari actual

31. Comandes de xarxa:
   - `ipconfig` → veure configuració IP
   - `ping google.com` → comprovar connexió
   - `netstat -an` → connexions obertes

32. Comandes interessants (una mica més avançades):
   - `tree` → veure estructura de carpetes
   - `cls` → netejar pantalla
   - `help` → veure ajuda
   - `shutdown /s /t 0` → apagar l'equip

33. Mini interpretació:
   - Indicar què mostra `tasklist`
   - Indicar què mostra `ipconfig`
   - Indicar què mostra `systeminfo`

---

# Fase 7 – Instal·lació d'aplicacions

34. Descarregar un programa des del navegador (ex: Chrome o VS Code)  
35. Instal·lar-lo seguint l'assistent  
36. Obrir-lo i comprovar que funciona  
37. Instal·lar una aplicació des de Microsoft Store  
38. Obrir-la i comprovar funcionament  
39. Desinstal·lar una aplicació: *Configuració → Aplicacions → Desinstal·lar*  
40. Verificació: *Comprovar que el programa ja no apareix al sistema* 
