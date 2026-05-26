# T10: Servidor d'Impressió Linux — CUPS (Tasca Individual)

## 📝 Breu Descripció

L'objectiu d'aquesta unitat és dissenyar i desplegar una **Prova de Concepte (PoC)** per a la centralització d'impressores utilitzant el sistema **CUPS (Common UNIX Printing System)** en un entorn corporatiu de la consultora *EverPia*. 

Amb aquesta solució s'optimitzen recursos, es redueixen costos de maquinari/tòner i es simplifica la gestió eliminant problemes de compatibilitat de *drivers* en xarxes híbrides (Ubuntu Server i clients Zorin OS).

---

## 🖥️ Escenari de Treball (PoC)

Per a la realització de la Prova de Concepte es reutilitzarà el mateix entorn de xarxa i màquines virtuals que a la pràctica de NFS:

* **Màquina 1 (Servidor):** `Ubuntu Server`
  * Interfície 1: Configurada en mode **NAT**.
  * Interfície 2: Configurada en mode **Host-Only** (Xarxa interna).
* **Màquina 2 (Client):** `Zorin OS` (Desktop)
  * Mateixa configuració de xarxa que el servidor per garantir la visibilitat.
* **Impresora Virtual:** Utilitzarem `cups-pdf`. Actua com una impressora física real, però "imprimeix" els treballs generant directament fitxers PDF emmagatzemats al servidor.

---

## 🛠️ Passos de la PoC (Prova de Concepte)

La resolució pràctica s'ha de dur a terme seguint aquesta seqüència cronològica:

1. **Instal·lació de CUPS:** Instal·lar el servei del servidor d'impressió a la màquina Ubuntu Server.
2. **Instal·lació de la impressora virtual:** Afegir el paquet necessari per disposar de l'emulador `cups-pdf`.
3. **Configuració de l'administració de CUPS:** Modificar els permisos per permetre que el dimoni CUPS escolti peticions a través de totes les interfícies de xarxa de la màquina.
4. **Compartició des del panell web:** Accedir a la interfície web de CUPS (`http://localhost:631` o via IP remota) per configurar i activar l'opció de compartir la impressora a la xarxa.
5. **Connexió des del client:** Afegir i enllaçar la impressora compartida des de l'entorn d'escriptori del client Zorin OS.
6. **Validació d'impressió:** Enviar diversos documents de prova des del client cap a la xarxa.
7. **Verificació al servidor:** Comprovar el directori de destí de CUPS al servidor per verificar la correcta generació dels fitxers PDF resultants dels treballs.

> 📊 **Requisit de lliurament:** Cal documentar exhaustivament totes les comandes utilitzades durant el procés (tal com s'especifica a la guia metodològica) i incloure les captures de pantalla clau que demostrin el correcte funcionament de cada pas.

---

## 📚 Materials i Links de Suport

* 📑 **UD5. AA1. CUPS** — *Disponibilitat:* Documentació teoricopràctica disponible al **Moodle** del mòdul de *Sistemes Operatius en Xarxa*.
* 🎥 **Instalación de servidor de impresión en CUPS para Linux** — [Vídeo tutorial a YouTube](https://www.youtube.com/watch?v=FNwSTrOSgZQ) de J.B. Alex Mantich (Guia pas a pas sobre Debian/Ubuntu, configuració web i gestió del *buffer*).
* 🌐 **Network File System (NFS) i Documentació Oficial** — [Ubuntu Server Documentation](https://documentation.ubuntu.com/server/how-to/networking/install-nfs/).
* 🌐 **How To Install CUPS Print Server on Ubuntu 24.04 LTS** — [Guia tècnica a Idroot](https://idroot.us/install-cups-print-server-ubuntu-24-04/).
