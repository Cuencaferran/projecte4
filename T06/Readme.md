🖥️ T06: Accés Remot — Escriptori Remot (RDP)
Guia Oficial per a Becaris de Suport Remot - EverPia
📘 1. Introducció

En aquesta tasca aprendràs a establir connexions d’Escriptori Remot (RDP), el protocol més utilitzat per connectar-se a equips Windows i, actualment, també compatible amb escriptoris GNU/Linux com Gnome o Zorin OS.

A EverPia no només administrem servidors; també donem suport a usuaris finals que sovint necessiten ajuda immediata. Quan un client diu:

"No em funciona el programa X"
"M’ha sortit un error a la pantalla"

… necessitem veure exactament el que ells veuen i interactuar amb el seu equip. Aquí entra en joc RDP.

Aquesta és la guia que faràs servir per crear connexions ràpides, eficients i sense errors.

🎯 2. Objectiu de la tasca

Crear una Prova de Concepte (PoC) i documentació clara sobre com utilitzar RDP per establir connexions a:

Windows Server

Windows 10/11

GNU/Linux amb escriptori Gnome (ex: Zorin OS)

La guia ha d'estar pensada per ser utilitzada per becaris sense experiència i per consultors que necessiten actuar amb rapidesa davant d’un client nerviós.

🧰 3. Materials necessaris

💻 Màquina virtual Windows (servidor o client)

🖥️ Màquina virtual GNU/Linux (Zorin, Ubuntu Gnome, etc.)

🔌 Protocol RDP activat

🌐 Accés a la xarxa local o NAT configurat

🔑 Credencials dels equips

🔗 Recursos: Moodle 0227 Serveis de Xarxa — UD4.AA3 Escriptoris Remots

🔐 4. Activació de RDP a Windows
4.1. Activar Escriptori remot

Obrir Configuració (Win + I)

Anar a Sistema → Escriptori remot

Activar l’opció Permet el control remot de l’equip

Confirmar a la finestra emergent

Verificar:

✔️ L'usuari té permisos RDP

✔️ El firewall permet el port 3389

4.2. Activar RDP via Panell de Control

Obre Sistema

Clica Configuració avançada del sistema

A la pestanya Accés remot:

Marca Permetre connexions només amb Escriptori remot amb Autenticació a nivell de xarxa

🪟 5. Connexió a un Windows amb RDP (des d’un altre Windows)
5.1. Utilitzar el client RDP

Obre el menú Inici

Escriu: mstsc

Introdueix:

IP/DNS de la màquina remota

Fes clic a Connecta

Escriu:

Usuari (ex: Administrador)

Contrasenya

Accepta l’avís de certificat

5.2. Consells pràctics

Si no connecta, prova:
ping IP_del_client

Si respon, però RDP no connecta, probablement és:

❌ Firewall bloquejant port 3389

❌ RDP desactivat

❌ L’usuari no té permisos

🐧 6. Connexió RDP a GNU/Linux (Gnome / Zorin OS)
6.1. Activar RDP (Gnome Remote Desktop)

Obrir Configuració

Anar a Compartició

Activar Compartició

Entrar a Escriptori remot

Activar:

Escriptori remot

Accés amb contrasenya

Opcional: activar Xifratge

➡️ Gnome utilitza el protocol RDP nativament des de GNOME 42.

6.2. Connexió des de Windows

Igual que abans:

mstsc → IP de Linux → Connecta → Contrasenya

🌐 7. Connexió RDP des de Linux a Windows

Et cal un client RDP, com per exemple:

remmina (recomanat)

krdc

freerdp

Instal·lació de Remmina:
sudo apt install remmina remmina-plugin-rdp

Connexió:

Obrir Remmina

Afegir nova connexió

Tipus: RDP

IP o hostname

Usuari i contrasenya

Connectar

🧪 8. PoC: Què ha d’incloure la teva documentació final

✔️ Captures de pantalla de cada pas
✔️ Com s’activa RDP a Windows
✔️ Com s’activa RDP a Linux (Gnome)
✔️ Com connectar des de Windows → Windows
✔️ Com connectar des de Windows → Linux
✔️ Com connectar des de Linux → Windows
✔️ Solució d’errors típics
✔️ Un estil clar, curt i orientat a “usuari nerviós”

🚑 9. Troubleshooting (errors habituals)
🔸 No puc connectar per RDP

Revisa que el port 3389 no està bloquejat

Comprova que el dispositiu està encès i a la mateixa xarxa

Revisa les credencials

🔸 Pantalla negra en connectar

La sessió de l’usuari pot estar bloquejada

L’acceleració gràfica pot causar conflictes

🔸 Certificat no fiable

Normal en connexions internes

Pots prémer Sí per continuar

🏁 10. Conclusió

Amb aquesta guia ja tens tots els passos necessaris per donar suport a clients i companys utilitzant Escriptori Remot (RDP) tant a Windows com a GNU/Linux.

Recorda:
La rapidesa i la claredat fan la diferència en una incidència remota.
