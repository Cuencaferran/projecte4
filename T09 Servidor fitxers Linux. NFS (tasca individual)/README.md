# Tasca 09: Servidor de Fitxers Linux — NFS (Tasca Individual) 📂🐧

## 🏢 El Cas Client: DevOptimize Solutions

El nostre client, **DevOptimize Solutions**, és una petita startup de desenvolupament de programari que treballa exclusivament en entorns Linux. Actualment s'enfronten a un problema crític: el codi font i els actius del projecte (documents de disseny, scripts) estan completament descontrolats. Cada desenvolupador treballa amb còpies locals, provocant errors constants de versions i una pèrdua d'eficiència massiva.

Ens han contractat per implementar un **servidor de fitxers centralitzat**. Com que tot l'entorn és 100% Linux, la solució nativa més ràpida i eficient és **NFS** (*Network File System*).

> ⚠️ **Condició clau del client:** DevOptimize Solutions **no** disposa d'un entorn d'autenticació centralitzada (com LDAP o Active Directory) i no té previst implementar-lo a curt termini. La demostració ha de reflectir aquesta realitat i evidenciar-ne les limitacions de seguretat de ID (`UID`/`GID`).

---

## 🎯 Objectius de la Demostració (PoC)

La teva missió individual és muntar un laboratori amb un **Servidor NFS (NFSv3)** i un **Client Linux** per demostrar el control d'accés, la gestió de permisos i el comportament del sistema.

### 🖥️ 1. Configuració del Servidor
- [ ] **Instal·lació:** Instalar els paquets del servidor NFS (`nfs-kernel-server`).
- [ ] **Estructura:** Crear les carpetes compartides i simular els usuaris/grups locals del client.
- [ ] **Permisos locals:** Assignar correctament els propietaris i permisos reals amb `chown` i `chmod`.
- [ ] **Exportació:** Configurar el fitxer `/etc/exports` per definir quines IPs tenen accés i amb quines opcions.

### 💻 2. Configuració del Client
- [ ] **Instal·lació:** Instal·lar els paquets del client (`nfs-common`).
- [ ] **Muntatge:** Crear els punts de muntatge locals i connectar-se als recursos compartits del servidor.
- [ ] **Proves d'Accés:** Comprovar com actua el servidor quan es creen o modifiquen fitxers des del client segons l'usuari actiu.

---

## ⚙️ Opcions clau de `/etc/exports` a provar

| Opció | Descripció |
| :--- | :--- |
| **`rw` / `ro`** | Permet l'accés de lectura i escriptura, o només lectura. |
| **`sync`** | Obliga al servidor a respondre a les peticions només quan els canvis s'han desat al disc (més segur). |
| **`root_squash`** | Mapeja les peticions del `root` del client cap a un usuari anònim sense privilegis (`nobody`) per seguretat. |
| **`no_root_squash`** | Permet al `root` del client mantenir els privilegis de `root` al servidor (perillós). |
| **`all_squash`** | Mapeja **tots** els usuaris del client a un únic usuari anònim. |

---

## 📚 Materials i Links de Suport

* 📁 **Material propi del Moodle:** `UD5. AA1. NFS` (Disponible a la plataforma d'Aules / Moodle).
* 🌐 [NFS (Parte 1): Instalación en un Servidor Ubuntu 20.04 LTS](https://somebooks.es/nfs-parte-1-instalacion-en-un-servidor-ubuntu-20-04-lts/) — *SomeBooks.es*
* 🌐 [NFS (Parte 2): Instalación en un Cliente Ubuntu 20.04 LTS](https://somebooks.es/nfs-parte-2-instalacion-en-un-cliente-ubuntu-20-04-lts/) — *SomeBooks.es*
* 🐧 [Network File System (NFS) Official Guide](https://documentation.ubuntu.com/server/how-to/networking/install-nfs/) — *Ubuntu Server Documentation*

---

## 🛠️ Enllaç al Repositori del Detall de la Tasca
Trobaràs el llistat detallat de les comprovacions exactes que has de fer i documentar en aquest repositori oficial de l'assignatura:
🔗 [https://github.com/SMX2n/Projecte04-NFS](https://github.com/SMX2n/Projecte04-NFS)