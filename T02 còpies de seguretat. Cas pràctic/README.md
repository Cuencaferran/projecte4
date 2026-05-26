🔵 Guia Tècnica – Còpies de Seguretat (Esquema 3-2-1)

Client: Muntatges i Serveis Tècnics SL
Document: Prova de concepte i guia d’implantació
Versió: 1.0

🖥️ PART 1 — Còpia de seguretat Windows 11 amb Duplicati
⚙️ 1. Preparació de la màquina virtual

Crear una VM amb Windows 11.

Afegir dos discos:

Disc 1: Sistema operatiu

Disc 2: 10 GB (destí còpies locals)

Crear o usar un compte de Google no escolar per la còpia al núvol.

📥 2. Instal·lació de Duplicati

Descarregar-lo de duplicati.com

Instal·lar amb valors per defecte

Accedir-hi via navegador:
👉 http://localhost:8200

💾 3. Còpia local cada hora
➕ Crear nova feina

Add backup → Configure a new backup

🔐 Paràmetres

Encriptació: AES-256

Origen: C:\Users\<usuari>\

Destí: D:\backup-local

⏱️ Planificació

Executar cada 1 hora

🧪 Prova

Afegir fitxers a Documents

Esperar execució o forçar Run now

☁️ 4. Còpia a Google Drive a les 18:00

Crear nova feina

Destination: Google Drive

Autoritzar el compte

Carpeta: /duplicati-backups

Schedule: cada dia a les 18:00

♻️ 5. Restauració des del disc secundari

Esborrar el contingut de Documents

A Duplicati → Restore

Seleccionar feina local

Restaurar a la ubicació original

🌐 6. Restauració des del núvol (Google Drive)

Duplicati → Restore

Seleccionar la feina de Drive

Escollir data/versió

Restaurar (a carpeta original o temporal)

🐧 PART 2 — Còpia de seguretat Linux amb Duplicity i Cron
💽 1. Preparació

Ubuntu Server

Afegir un disc de 10 GB

📀 2. Inicialització i muntatge del disc
sudo fdisk /dev/sdb      # crear partició
sudo mkfs.xfs /dev/sdb1  # formatar en xfs
sudo mkdir -p /media/backup
sudo mount /dev/sdb1 /media/backup

📦 3. Instal·lació de Duplicity
sudo apt update
sudo apt install duplicity

👤 4. Crear usuaris i fitxers de prova
Crear usuaris:
sudo adduser user1
sudo adduser user2

Crear fitxers de 10 MB:
mkdir ~/test
cd ~/test
for i in {1..4}; do
  dd if=/dev/zero of=file$i bs=1M count=10
done

🔒 5. Fer un backup complet de /home
duplicity /home file:///media/backup/full

🗑️ 6. Esborrar i restaurar
Eliminar arxius:
rm ~/test/file*

Restauració:
duplicity restore file:///media/backup/full /home

➕ 7. Còpia incremental
Afegir fitxer:
dd if=/dev/zero of=~/test/newfile bs=1M count=4

Executar incremental:
duplicity incremental /home file:///media/backup/full

⏏️ 8. Desmuntar la unitat
sudo umount /media/backup

🤖 Automatització amb scripts i cron
📜 9. Script de còpia completa (fullbackup.sh)

Ubicació: /usr/local/bin/fullbackup.sh

#!/bin/bash
export PASSPHRASE="contrasenya"

mount /dev/sdb1 /media/backup

duplicity full /home file:///media/backup/full

umount /media/backup


Permisos:

sudo chmod +x /usr/local/bin/fullbackup.sh

⏰ 10. Programació al cron (diumenge 23:00)
sudo crontab -e


Afegir:

0 23 * * 0 /usr/local/bin/fullbackup.sh

📜 11. Script còpia incremental (incrementalbackup.sh)

Ubicació: /usr/local/bin/incrementalbackup.sh

#!/bin/bash
export PASSPHRASE="contrasenya"

mount /dev/sdb1 /media/backup

duplicity incremental /home file:///media/backup/full

umount /media/backup


Permisos:

sudo chmod +x /usr/local/bin/incrementalbackup.sh

⏱️ 12. Programació incremental (dl–ds, 23:00)
sudo crontab -e


Afegir:

0 23 * * 1-6 /usr/local/bin/incrementalbackup.sh
