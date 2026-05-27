# Tasca 02: DPR — Còpies de Seguretat. Cas Pràctic 💾

## 🏢 Introducció al Cas: Muntatges i Serveis Tècnics SL

A partir de la política de còpies de seguretat dissenyada en la tasca anterior per al nostre client **"Muntatges i Serveis Tècnics SL"**, passem a l'acció. El client sol·licita l'elaboració de **guies tècniques amb proves de concepte (PoC)** perquè el seu personal estigui capacitat per implantar el pla de còpies de seguretat final.

---

## 🪟 Part 1: Còpia de Seguretat en Equips Clients Windows

Es demana una excepció en el DPR per a l'equip Windows del **Director de l'empresa**, on es guarda informació crítica localment. S'aplicarà una estratègia **3-2-1** utilitzant l'eina **Duplicati**:
* **Còpia Local:** A un disc secundari de l'equip (Cada hora).
* **Còpia Cloud:** A un compte de Google Drive (Cada dia a les 18:00).

### 📝 Objectius i Proves de Concepte (Windows 11):
- [ ] **Configuració de l'entorn:** Crear MV Windows 11 amb disc principal (SO) i disc secundari de 10 GB.
- [ ] **Instal·lació:** Documentar el procés d'instal·lació de **Duplicati**.
- [ ] **Planificació:** Configurar els dos plans de còpies (Perfil d'usuari: per hores al disc local i a les 18:00 al Cloud).
- [ ] **Simulació de dades:** Afegir arxius de prova a la carpeta `Documents`.
- [ ] **Restauració Local:** Esborrar el contingut de `Documents` i restaurar des del disc secundari de 10 GB.
- [ ] **Restauració Cloud:** Comprovar i simular la restauració des de Google Drive.

---

## 🐧 Part 2: Còpia de Seguretat en Servidor Linux

Per al servidor Linux s'utilitzarà **Duplicity**, una eina CLI robusta que permet còpies locals i remotes, automatitzada mitjançant el programador de tasques **Cron**.

### 🛠️ Fases de la Guia Tècnica (Ubuntu Server + Disc 10 GB auxiliar):

| Pas | Acció Tècnica | Descripció / Comanda |
| :---: | :--- | :--- |
| **1** | Inicialització de la unitat | Formatar el segon disc en **XFS** i muntar manualment a `/media/backup`. |
| **2** | Instal·lació de l'eina | Instal·lar `duplicity` al sistema. |
| **3** | Generació de dades | Crear usuaris i generar 4 arxius de 10 MB a la `/home` de l'usuari amb `dd` o similar. |
| **4** | Còpia inicial | Realitzar una còpia de seguretat completa de la carpeta `/home`. |
| **5** | Prova de desastre | Esborrar els arxius i executar un `restore` per comprovar la recuperació. |
| **6** | Còpia Incremental | Afegir un fitxer nou de 4 MB, llançar una nova còpia i comprovar el comportament incremental. Desmuntar la unitat. |

### 🤖 Automatització amb Scripts i Cron
Per seguretat, la unitat de backup ha d'estar desmuntada per defecte. Els scripts han de muntar la unitat al principi i desmuntar-la en acabar.

- [ ] **Script Complet (`fullbackup.sh`):** Realitza la còpia completa de `/home`. Ha d'utilitzar la variable d'entorn `export PASSPHRASE=contrasenya` per automatitzar la clau. Donar permisos d'execució.
- [ ] **Programació Full:** Programar al Cron de `root` els **diumenges a les 23:00**.
- [ ] **Script Incremental (`incrementalbackup.sh`):** Realitza còpies incrementals de `/home` amb la mateixa variable `PASSPHRASE`.
- [ ] **Programació Incremental:** Programar al Cron de `root` de **dilluns a dissabte a les 23:00**.

---

## 🔗 Materials i Links de Suport

* 🌐 [Web Oficial de Duplicati](https://duplicati.com/)
* 📄 [Creando archivos con fsutil (Windows)](https://waytoit.wordpress.com/2015/03/15/creando-archivos-con-fsutil/)
* 📄 [Creando archivos de prueba en Linux](https://waytoit.wordpress.com/2015/03/21/creando-archivos-de-prueba-en-linux/)
* 🐧 [Duplicity Man Page (Ubuntu)](http://manpages.ubuntu.com/manpages/trusty/man1/duplicity.1.html)
* ⏰ [Programar tareas en Linux usando Crontab](https://geekytheory.com/programar-tareas-en-linux-usando-crontab)

---

## 📋 Entregables recomanats en aquesta carpeta
* **`guia_windows.md`**: Passos, captures de Duplicati i proves de restauració.
* **`guia_linux.md`**: Comandes utilitzades, captures de Duplicity i configuració del Crontab.
* **`scripts/`**: Carpeta amb els fitxers `fullbackup.sh` i `incrementalbackup.sh`.