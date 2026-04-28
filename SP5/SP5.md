
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

<img width="935" height="776" alt="image" src="https://github.com/user-attachments/assets/6323c421-3bb9-4be2-a175-eb73eb537f3b" />


<img width="720" height="497" alt="image" src="https://github.com/user-attachments/assets/897e951b-13c2-42c7-8b23-a4c2d25d130d" />

- No apareix el Mozilla instal·lat, però al restaurar sol esborres instal·lacions i programes, els documents no s'esborren.

<img width="787" height="502" alt="image" src="https://github.com/user-attachments/assets/1aceb2ea-27af-4289-a351-331e6589eb78" />

---

# Fase 3 – Llicències de Windows

11. Obrir Configuració → Sistema → Activació

<img width="829" height="485" alt="image" src="https://github.com/user-attachments/assets/48202151-234d-4cbe-b49f-5dabebc3c6a9" />

12. Veure si Windows està activat

<img width="830" height="602" alt="image" src="https://github.com/user-attachments/assets/0290cf9e-7962-4abc-8cfa-79e47e791d34" />

13. Executar al cmd: `slmgr /xpr`

<img width="754" height="524" alt="image" src="https://github.com/user-attachments/assets/5ff1f0be-4065-425c-8485-b16ec9c3368e" />

14. Esbrinar llicenciament Windows i explicar breument

Aixó voldría dir que el sistema detecta que no hi ha llicència o està desactivada o expirada.

15. Consultar preu aproximat d'una llicència Windows (web oficial o botigues)

<img width="1814" height="950" alt="image" src="https://github.com/user-attachments/assets/1b625767-3507-457b-a01c-34de90d99d64" />


---

# Fase 4 – Gestor d'arrencada

16. Obrir Command Prompt com administrador

<img width="804" height="685" alt="image" src="https://github.com/user-attachments/assets/df49fec1-ce31-45ef-97e6-144ebaa83e5e" />

<img width="804" height="685" alt="image" src="https://github.com/user-attachments/assets/726cec73-ec87-4220-a34a-a0fac127c908" />

 
17. Executar `bcdedit`

<img width="804" height="685" alt="image" src="https://github.com/user-attachments/assets/b51aefec-08f3-44d2-a646-b630ed95311e" />
 
18. Identificar els blocs:
   - Administrador de arranque de Windows (Boot Manager)

<img width="578" height="225" alt="image" src="https://github.com/user-attachments/assets/3d121f8f-5e12-4c8f-a792-b48c0495976a" />

   - Cargador de arranque de Windows (Boot Loader)

<img width="593" height="316" alt="image" src="https://github.com/user-attachments/assets/8cb3c4a0-1cd0-444e-9a0b-5e126ba2e55f" />

19. Interpretar dades concretes

## Del bloc Boot Manager, identificar:

- `default {current}` → Quin sistema operatiu arrenca per defecte, es a dir, aquest.  
- `timeout 30` → temps d'espera abans d'arrencar, 30 segons exactament.

## Del bloc Boot Loader, identificar:

- `device partition=C:` → Partició del disc on està instal·lat Windows.  
- `path \Windows\system32\winload.efi` → fitxer que carrega el sistema durant l'arranc del sistema .
- `description Windows 11` → nom del sistema operatiu que surt al gestor d'arranc . 

20. Respondre preguntes curtes:
   - Quin sistema s'està arrencant: S'està arrancant el Windows 11 
   - A quin disc o partició està instal·lat: al partition=C:
   - Quant temps espera abans d'arrencar: 30 segons espera
   - Quin fitxer inicia Windows: el arxiu de winload.efi

21. Interpretació final. *Explicar amb una frase:*
   - Qui decideix l'arrencada (Boot Manager): Es el boot manager el que decideix quin sistema operatiu s'acaba iniciat 
   - Qui carrega el sistema (Boot Loader): El Boot Loader carrega el sistema i s'encarrega també de carregar tots els fitxer que es necessiten per a iniciar tot el sistema.

---

# Fase 5 – Xarxa bàsica

22. Obrir configuració de xarxa

<img width="892" height="704" alt="image" src="https://github.com/user-attachments/assets/b43914b6-ac87-4159-b622-129f8e540263" />
   
24. Consultar IP amb: `ipconfig`

<img width="892" height="704" alt="image" src="https://github.com/user-attachments/assets/fd59e93a-70dc-4755-b0ee-9194fa7866b4" />

    
25. Configurar IP dinàmica (DHCP automàtic)

<img width="777" height="305" alt="image" src="https://github.com/user-attachments/assets/1bab4829-0dec-4c27-92da-10dc797a2ba0" />

<img width="777" height="305" alt="image" src="https://github.com/user-attachments/assets/05f3ffd9-9f50-487e-991e-6385679c172e" />


26. Configurar IP fixa (manual: IP, màscara, gateway, DNS)+

<img width="859" height="509" alt="image" src="https://github.com/user-attachments/assets/4a0d67e6-1fcb-48c0-8d8b-79c7ed9bdcfc" />

<img width="845" height="506" alt="image" src="https://github.com/user-attachments/assets/b4493338-45e7-459c-9ffc-f6028cc8541c" />

<img width="845" height="506" alt="image" src="https://github.com/user-attachments/assets/29b2ed7e-306b-41cb-b82d-106b75e5818b" />

   
27. Comprovar connexió amb: `ping google.com`  

<img width="854" height="302" alt="image" src="https://github.com/user-attachments/assets/600995c7-5513-4118-9202-ccaae63e376f" />

---

# Fase 6 – Comandes generals

28. Obrir PowerShell

<img width="1014" height="426" alt="image" src="https://github.com/user-attachments/assets/74b406f6-0ebd-45fa-8ae7-650a76030eb8" />

29. Diferenciar cmd i PowerShell:
   - `cmd` → comandes bàsiques i clàssiques

<img width="1014" height="426" alt="image" src="https://github.com/user-attachments/assets/cf0dd2f9-1832-4ece-84ec-bd4fd25fb783" />

   - `PowerShell` → més potent, permet treballar amb objectes i automatitzar tasques

<img width="1014" height="426" alt="image" src="https://github.com/user-attachments/assets/1a64edbd-1fa9-423d-a371-2f72b8ca182a" />


30. Comandes bàsiques (provar-les):
   - `dir` → veure fitxers

   <img width="602" height="540" alt="image" src="https://github.com/user-attachments/assets/d17b6800-2d01-4011-b40c-bd3179c423d4" />

   - `cd` → moure's per carpetes

<img width="211" height="72" alt="image" src="https://github.com/user-attachments/assets/779a9352-57eb-4067-90ee-b5d5a78dd8c9" />

   - `mkdir prova` → crear carpeta

<img width="684" height="346" alt="image" src="https://github.com/user-attachments/assets/4c65c2ed-1679-4922-a8e8-27c9a9afc3b3" />


   - `echo hola > fitxer.txt` → crear fitxer

<img width="882" height="529" alt="image" src="https://github.com/user-attachments/assets/6a36e3f8-fb32-41f1-9c29-5d7a43599d2a" />

   - `del fitxer.txt` → eliminar fitxer

<img width="882" height="529" alt="image" src="https://github.com/user-attachments/assets/05dfb5d3-d400-496d-852c-b33b74d8320f" />


31. Comandes útils del sistema:
   - `tasklist` → veure processos actius

<img width="882" height="529" alt="image" src="https://github.com/user-attachments/assets/22c8bcf8-d550-4264-a4c9-7cba54c2d9b6" />

   - `taskkill /IM notepad.exe /F` → tancar un procés

<img width="818" height="122" alt="image" src="https://github.com/user-attachments/assets/a24ed9d0-278a-4fc6-8cc8-65531e9b64d5" />
   
   - `systeminfo` → informació completa del sistema

<img width="981" height="604" alt="image" src="https://github.com/user-attachments/assets/1bdd8a4d-3b10-4802-86d4-e821bb42d1d2" />

   - `hostname` → nom de l'equip

<img width="254" height="104" alt="image" src="https://github.com/user-attachments/assets/7ca20d3b-be38-460c-9196-1d7b27346aba" />

   - `whoami` → usuari actual
     
<img width="254" height="104" alt="image" src="https://github.com/user-attachments/assets/bb458dcf-3ce6-4047-b1a4-67acfbfd5afb" />


31. Comandes de xarxa:
   - `ipconfig` → veure configuració IP
     
<img width="667" height="248" alt="image" src="https://github.com/user-attachments/assets/7bc330ad-8d6f-414a-8f57-565796f1a5f8" />

   - `ping google.com` → comprovar connexió

<img width="678" height="270" alt="image" src="https://github.com/user-attachments/assets/e6af18ee-a9e0-4f1d-af48-93324ad0ac82" />

   - `netstat -an` → connexions obertes

<img width="720" height="543" alt="image" src="https://github.com/user-attachments/assets/564f033f-3b4d-4d7c-a2c4-5e51b4f978cd" />


32. Comandes interessants (una mica més avançades):
   - `tree` → veure estructura de carpetes

 <img width="715" height="377" alt="image" src="https://github.com/user-attachments/assets/2702cf7d-2caa-4b90-9ca0-b2c6c156049b" />
 
   - `cls` → netejar pantalla

<img width="715" height="377" alt="image" src="https://github.com/user-attachments/assets/ad293517-4067-4a6a-8505-936627f68330" />

   - `help` → veure ajuda

<img width="746" height="554" alt="image" src="https://github.com/user-attachments/assets/260b58dd-6d95-47f2-8dac-c6b5d550d5f9" />

   - `shutdown /s /t 0` → apagar l'equip

<img width="746" height="554" alt="image" src="https://github.com/user-attachments/assets/ca58f976-c931-4e2e-ac60-629ddf2bc5e3" />


33. Mini interpretació:
   - Indicar què mostra `tasklist`: mostra totes les aplicacions i serveis en curs, el tipic administrador de tasques
   - Indicar què mostra `ipconfig`: mostra la Configuració de la xarxa, IP, DNS, IPv4
   - Indicar què mostra `systeminfo`: mostra totes les característiques del sistema, cpu, recursos, processador...

---

# Fase 7 – Instal·lació d'aplicacions

34. Descarregar un programa des del navegador (ex: Chrome o VS Code)
    
<img width="1029" height="699" alt="image" src="https://github.com/user-attachments/assets/5c57c45d-9d0f-477a-952e-7ff869f22c5c" />
  
35. Instal·lar-lo seguint l'assistent

<img width="1029" height="699" alt="image" src="https://github.com/user-attachments/assets/32744a89-13a5-42ed-982c-3afbe5f85f20" />

36. Obrir-lo i comprovar que funciona

<img width="1029" height="699" alt="image" src="https://github.com/user-attachments/assets/5ffc87b3-55ea-4e7f-a68c-d858a4c2b4c2" />

<img width="1029" height="699" alt="image" src="https://github.com/user-attachments/assets/db28973a-e947-4d22-a347-56bdd741c8e9" />

37. Instal·lar una aplicació des de Microsoft Store

<img width="851" height="630" alt="image" src="https://github.com/user-attachments/assets/c4f9ac3b-e9cd-4793-baf5-bcf0c15c9556" />

<img width="851" height="630" alt="image" src="https://github.com/user-attachments/assets/c77410ce-c1a6-4393-a455-10bf96bc4f90" />


38. Obrir-la i comprovar funcionament

<img width="1027" height="814" alt="image" src="https://github.com/user-attachments/assets/2fca0fc3-dd0f-4f9d-af14-7f98d3494428" />

39. Desinstal·lar una aplicació: *Configuració → Aplicacions → Desinstal·lar*

<img width="1027" height="814" alt="image" src="https://github.com/user-attachments/assets/cd7f2b83-28cf-4f72-999f-8bbd9c405d7e" />

<img width="831" height="650" alt="image" src="https://github.com/user-attachments/assets/08108018-bdd9-41a9-acd0-2eec8ac78044" />

<img width="831" height="650" alt="image" src="https://github.com/user-attachments/assets/819d6b0e-a61c-4894-a703-1cd0ec77b919" />

40. Verificació: *Comprovar que el programa ja no apareix al sistema*

<img width="831" height="650" alt="image" src="https://github.com/user-attachments/assets/40f45f23-d9d4-424e-89a1-4d20c119ce08" />

