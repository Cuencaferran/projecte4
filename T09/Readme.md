🗂️ T09: Servidor de fitxers Linux — NFS (tasca individual)
📌 Breu descripció

Aquesta activitat consisteix en desplegar un servidor NFS (versió 3) i un client Linux per demostrar la centralització de dades en entorns Linux. Es treballarà amb usuaris locals, ja que el client no disposa d’un sistema d’autenticació centralitzat.

🧩 Introducció

L’empresa DevOptimize Solutions, una startup de desenvolupament de programari que treballa exclusivament amb Linux, pateix problemes de:

dispersió del codi font

documents duplicats

descontrol de versions

pèrdues d’eficiència

Per solucionar-ho, ens han contractat per implantar un servidor de fitxers centralitzat.

Atès que tot l’entorn és Linux, la solució òptima és:

🔧 NFS (Network File System)

Solució nativa, ràpida i eficient per compartir fitxers en entorns Unix/Linux.

El client insisteix que no utilitza cap servei d’identitat centralitzat (LDAP, AD, etc.), així que la gestió d’usuaris serà local.

🎯 Objectiu de la tasca

Has de muntar una demostració funcional que inclogui:

🖥️ Servidor NFS

Instal·lació i configuració d’un servei NFSv3

Definició d’exports al fitxer /etc/exports

Aplicació d'opcions de control d’accés (rw, ro, sync, no_root_squash...)

💻 Client Linux

Configuració del client NFS

Muntatge del recurs compartit manualment i/o automàticament (fstab)

👥 Usuaris i permisos

Creació d’usuaris i grups per simular el client real

Gestió de permisos amb:

chmod

chown

corresponents UID/GID

Demostració de com NFS gestiona els accessos sense autenticació centralitzada

📁 Repositori de la tasca

➡️ https://github.com/SMX2n/Projecte04-NFS

Trobaràs tota la descripció completa i passos a seguir.

📚 Materials i links de suport
📘 Material del curs

UD5. AA1. NFS
(Disponible al Moodle del mòdul de Sistemes Operatius en Xarxa)

🌐 Guies i tutorials recomanats

Instal·lació del servidor NFS a Ubuntu 20.04 LTS
Ruiz, P. (2021)
https://somebooks.es/nfs-parte-1-instalacion-en-un-servidor-ubuntu-20-04-lts/

Instal·lació del client NFS
Ruiz, P. (2021)
https://somebooks.es/nfs-parte-2-instalacion-en-un-cliente-ubuntu-20-04-lts/

Documentació oficial d’Ubuntu Server — NFS
https://documentation.ubuntu.com/server/how-to/networking/install-nfs/

📝 Resultat esperat

Un entorn funcional on es pugui demostrar al client:

com es comparteixen carpetes via NFS

com es controlen els accessos segons usuaris, grups i opcions d’exportació

quines limitacions té un sistema sense autenticació centralitzada

que el seu entorn podria millorar la coherència i eficiència del treball
