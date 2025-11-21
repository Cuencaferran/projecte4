Guia tècnica – Còpies de seguretat (Esquema 3-2-1)

Client: Muntatges i Serveis Tècnics SL
Document: Prova de concepte i guia d’implantació
Autor: —
Versió: 1.0

🔵 PART 1 — Còpia de seguretat en Windows 11 amb Duplicati
1. Preparació de la màquina virtual

Crear una VM Windows 11.

Afegir dos discos:

Disc 1 → Sistema operatiu

Disc 2 (10 GB) → Destí de còpies locals

Crear o usar un compte de Google no escolar per l’emmagatzematge al núvol.

2. Instal·lació de Duplicati

Descarregar des de: https://duplicati.com

Instal·lar l’aplicació amb valors per defecte.

Duplicati s’executarà a la barra del sistema → accedir via navegador:
http://localhost:8200

3. Configuració del pla de còpia local (cada hora)
3.1. Crear nova feina

Add backup → Configure a new backup

3.2. Opcions principals

Encryption: AES-256, posar una contrasenya segura.

Source data: C:\Users\<usuari>\ (especialment Documents, Desktop, etc.)

Destination:

Tipus: Local folder or drive

Carpeta: D:\backup-local

3.3. Planificació

Every 1 hour

3.4. Prova

Crear alguns fitxers a Documents.

Esperar una hora o executar manualment Run now.

4. Configuració de la còpia al núvol (Google Drive, a les 18:00)
4.1. Nova feina

Add backup → Configure a new backup

4.2. Paràmetres

Destination: Google Drive
→ “AuthID” → iniciar sessió al compte personal de Google.

Folder: /duplicati-backups

4.3. Planificació

Daily at 18:00

5. Restauració des del disc secundari
5.1. Esborrar contingut

Ves a Documents

Esborra tots els fitxers.

5.2. Restauració

Duplicati → Restore

Selecciona la feina de còpia local

Escull la versió desitjada

Restaurar a la ubicació original

Verificar que els fitxers reapareixen.

6. Restauració des de Google Drive

Duplicati → Restore

Seleccionar la feina de Google Drive

Tria la versió (número de còpia o data)

Restaurar a la carpeta original o una carpeta temporal per verificació.

🔵 PART 2 — Còpia servidor Linux amb Duplicity + cron
1. Preparació de la màquina virtual

Crear una VM Ubuntu Server.

Afegir un disc de 10 GB.

2. Inicialització i muntatge del disc
2.1. Crear partició
sudo fdisk /dev/sdb
# n → nova partició
# w → guardar

2.2. Format xfs
sudo mkfs.xfs /dev/sdb1

2.3. Crear punt de muntatge
sudo mkdir -p /media/backup

2.4. Muntar la unitat
sudo mount /dev/sdb1 /media/backup

3. Instal·lació de Duplicity
sudo apt update
sudo apt install duplicity

4. Creació d’usuaris i fitxers de prova
4.1. Crear usuaris
sudo adduser user1
sudo adduser user2

4.2. Crear fitxers de 10 MB

A la carpeta de l’usuari principal:

mkdir ~/test
cd ~/test
for i in {1..4}; do
  dd if=/dev/zero of=file$i bs=1M count=10
done

5. Fer un backup complet de /home
duplicity /home file:///media/backup/full

6. Esborrar arxius i restaurar
6.1. Elimina els fitxers
rm ~/test/file*

6.2. Restauració
duplicity restore file:///media/backup/full /home

7. Crear un arxiu nou i backup incremental
dd if=/dev/zero of=~/test/newfile bs=1M count=4
duplicity incremental /home file:///media/backup/full

8. Desmuntar la unitat
sudo umount /media/backup

Automatització amb scripts + cron
8. Script fullbackup.sh (còpia completa)
Fitxer: /usr/local/bin/fullbackup.sh
#!/bin/bash

export PASSPHRASE="contrasenya"

mount /dev/sdb1 /media/backup

duplicity full /home file:///media/backup/full

umount /media/backup

Permisos
sudo chmod +x /usr/local/bin/fullbackup.sh

9. Programació al cron (diumenge 23:00)
sudo crontab -e


Afegir:

0 23 * * 0 /usr/local/bin/fullbackup.sh

10. Script incrementalbackup.sh
Fitxer: /usr/local/bin/incrementalbackup.sh
#!/bin/bash

export PASSPHRASE="contrasenya"

mount /dev/sdb1 /media/backup

duplicity incremental /home file:///media/backup/full

umount /media/backup

Permisos
sudo chmod +x /usr/local/bin/incrementalbackup.sh

11. Programació al cron (dl-ds, a les 23:00)
sudo crontab -e


Afegir:

0 23 * * 1-6 /usr/local/bin/incrementalbackup.sh
