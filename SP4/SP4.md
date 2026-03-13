# MONITORITZACIÓ, CONNEXIÓ REMOTA I LLICENCIAMENT


**##Teoria MONITORTIZACIÓ**

logger[opcions][-p prioritat][missatge]

logger -i -s -p mail.err Aturant el sistema

Server.prioritat accio

**- Serveis**
  
**auth**
**mail**
**lpr**
**cron**
**kern**

**- Prioritats dels serveis**


Prioritat de menos a més important, per exemple si posem Mail.alert ---> sera que la prioritat sera del nivell cap a dalt, soigue de alert a emerg,panic.
Si fiques Mail.=alert sera sol aquesta. SI fiquem *.crit es per a tots

**debug**
**infor**
**notice**
**warning,warn**
**err,error**
**crit**
**alert**
**emerg,panic**

-----------------------------------------------------------------------

Explicar una mica aixó la monitoritzacio i després entrar per exemple al firefox i mirar que consumeix, la prioritat, etc.

<img width="842" height="718" alt="image" src="https://github.com/user-attachments/assets/9df6f9c2-6475-4292-99fe-bd7cac0bacf8" />

<img width="842" height="718" alt="image" src="https://github.com/user-attachments/assets/f3818018-fe5a-4c42-860e-cc6471a16928" />

<img width="842" height="718" alt="image" src="https://github.com/user-attachments/assets/2c648192-d2d0-4285-bbc0-d893c1cba736" />

**LOGS**

- Entrar als LOGS ---> cd /var/log

EXPLICAR QUE VEEM, logs que poden no estar tots aqui, pero estiran tots als syslog ja q queda tot a aquest arxiu:



<img width="842" height="718" alt="image" src="https://github.com/user-attachments/assets/df2b32a4-686d-447b-b770-2dee90b9b3e5" />

quan trobem dmesg.1.gz i els altres això significa que es la rotació de logs, va guardant logs i va  Dintre de nano /etc/logrotate.conf podem decidir el temps de rotació de logs dels serveis en general.

Amb cd /etc/logrotate.d/ serveix per si es vol canviar la rotació dels logs fent el canvi de manera personalitzada de la rotació crean un arxiu i personalitzant-lo


-Obrim dos terminals

- Amb aquesta commanda, podem fer proves forçant logs:

<img width="724" height="262" alt="image" src="https://github.com/user-attachments/assets/d7365d4b-c2e5-4f2f-bb61-a1a4eaf950ca" />

- Després amb l'altra terminal entrem a aquest axriu:

<img width="599" height="47" alt="image" src="https://github.com/user-attachments/assets/3049a3e1-b16b-4575-8d3b-da5368c9c1ef" />

Aqui amb el *.* decidim que tot anirà al syslog 

<img width="598" height="31" alt="image" src="https://github.com/user-attachments/assets/9b150846-c9ec-4564-87d2-cac41d65f1dc" />

- Creem una prova
 
<img width="795" height="606" alt="image" src="https://github.com/user-attachments/assets/dee09f2b-1d02-4894-9eee-399bf1ba327d" />

- entrem al rsyslog i li canviem la prioritat al mail i despres reiniciem el syslog

<img width="795" height="292" alt="image" src="https://github.com/user-attachments/assets/cd8a3bd4-a3ed-44a7-9fd1-8e63ce77f8d3" />

<img width="795" height="292" alt="image" src="https://github.com/user-attachments/assets/47eb2a92-14ec-488d-92ef-3c0f22e5fdf2" />

- Ara fem la prova i al cat mail.log no tindria que sortir el canvi, pero al syslog si:

<img width="775" height="419" alt="image" src="https://github.com/user-attachments/assets/79b4f521-16d4-446d-bc93-15582093f119" />

- Ara cambien a mail.=crit, reiniciem el syslog  i fem la prova i solament al mail.log se veura el de la prioritat crit els altres sol al syslog per tant sol veura el 7 , el 5 i 6 sol al syslog

<img width="758" height="299" alt="image" src="https://github.com/user-attachments/assets/e4a22612-a512-470f-9741-717d9187ffc0" />

<img width="758" height="572" alt="image" src="https://github.com/user-attachments/assets/6e839e4c-9906-4309-9b4f-b318a5b1a7b0" />

- ara agregem aquesta commanda primera i reiniciem syslog, al crear el aitor.log nou, farem una prova amb diferents prioritats:

<img width="722" height="83" alt="image" src="https://github.com/user-attachments/assets/db28b764-87e3-440b-addd-3b34c6cc6455" />

<img width="805" height="451" alt="image" src="https://github.com/user-attachments/assets/ee35c4c4-6898-453f-8329-1d0dd93deac4" />


**Exercici**: simular servidor de logs centralitzat, a una maquina actuara com a srver i l'altra rebra logs del client

**Part server**

- Primer que tot, obro la maquina que simula el server i poso nano /etc/rsyslog.conf i es descomenten aquestes dos linies i després reiniciem amb systemctl restart syslog:
  
<img width="825" height="87" alt="image" src="https://github.com/user-attachments/assets/9a81e49f-bb00-4904-a205-5cf4de02f894" />

- mirem la ip del server en 1p a:

<img width="909" height="149" alt="image" src="https://github.com/user-attachments/assets/7a29918b-a524-4b1b-9af2-a649f4e60c53" />


**Part Client**

- Ara entrem --> nano /etc/rsyslog.d/50-default.conf, i al final de tot posem *.* la ip del server:514 (que son els ports que hem obert junt amb la ip que apuntarà)

<img width="909" height="412" alt="image" src="https://github.com/user-attachments/assets/e71bd7ce-c841-47f4-a9fd-aa8a7e928316" />

- Ara reiniciem systemctl restart syslog.

- Per últim farem una prova ---> farem una prova amb logger -i -s -p cron.alert dient que aquest SI que tindria que sortir, i a la màquina del server fem un tail del syslog per veure si ens surt el log amb l'avis del servei:

<img width="1625" height="831" alt="image" src="https://github.com/user-attachments/assets/c47e0f37-970b-4c49-8fa7-2de9d73dc95b" />

- Veem que surt el log correctament al servidor, fem una altra prova:

<img width="1784" height="402" alt="image" src="https://github.com/user-attachments/assets/9baaff45-fedd-4ada-8ae7-5286d8ff26ed" />

  

