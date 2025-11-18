# T01: DRP — Còpies de Seguretat · Estudi Cas Client (Treball Cooperatiu)
📌 Breu Descripció
Introducció

La primera hora el vostre responsable de seguretat us presenta el tema de les còpies de seguretat a partir d’un material didàctic. Després, haureu de treballar els aspectes més importants del tema mitjançant una dinàmica cooperativa.

🏭 Presentació del Cas Client

Empresa: "Muntatges i Serveis Tècnics SL"
Activitat: Instal·lació i manteniment d’equips industrials.

Infraestructura Tècnica

Servidor de Fitxers (Ubuntu Server) amb informació crítica:

Documents de Projectes: Plànols, especificacions (300 GB, creixement moderat).

Bases de Dades: Comptabilitat i clients (20 GB, canvi constant).

Carpetes Personals d’Usuaris: Documents de treball (100 GB).

10 Equips Clients (Windows 10/11):
Els usuaris treballen majoritàriament al servidor, però alguns guarden informes temporals a Documents.

Connexió a Internet: Fibra òptica 600 Mbps simètrica.

⏱️ Requisits de Recuperació

RTO (Temps de Recuperació):
Les dades de Comptabilitat/Clients han d’estar disponibles en menys de 4 hores.

RPO (Pèrdua de dades admesa):

Dades generals → pèrdua màxima de 24 h

Comptabilitat/Clients → pèrdua màxima de 4 h

Retenció:
Cal conservar les dades mínim 1 mes.

🧩 Fase 1: Treball Individual

Cada alumne respon de manera individual:

1. Què copiar? (Priorització)

Quines dades són més crítiques del servidor?

Cal fer còpia dels 10 equips clients? Justifica-ho.

2. Periodicitat i Tipus de Còpia

Proposa un calendari setmanal indicant si serà:

Completa

Diferencial

Incremental

3. Mitjans i Ubicació

Quin suport s’utilitzarà? (HDD externs, NAS, Cloud, Cintes...)

Segons la regla 3-2-1, on ha d’estar la còpia més recent?

👥 Fase 2: Treball per Parelles
1. Discussió i Consens

Les parelles comparen les seves respostes individuals i decideixen què mantenir, modificar o unificar.

2. Proposta Unificada — Esquema 3-2-1

Heu d’omplir aquesta taula:

Element	Proposta de la Parella	Justificació
Dades Crítiques		
Periodicitat (BD)		
Tipus de Còpia (BD)		
Mitjà 1 (Local)		
Mitjà 2 (Extern)		
👨‍🏫 Fase 3: Treball en Grup
1. Debat i Selecció

Cada parella presenta el seu esquema. El grup comenta:

Pros i contres

Cost

Seguretat

Temps de recuperació

Simplicitat

2. Política Final de Còpies de Seguretat

El grup redacta la proposta final per a l’empresa Muntatges i Serveis Tècnics SL.

📄 Document Final (Fase 3)

El document final ha d’incloure:

1) Dades Objecte de Còpia

Separar:

Servidor: Dades crítiques / no crítiques

Clients: Què es copia i amb quina freqüència

2) Cronograma Setmanal Detallat
Dia	Dades	Tipus de Còpia	Mitjà
Dilluns			
Dimarts			
Dimecres			
Dijous			
Divendres			
Dissabte			
Diumenge			
3) Elecció de Mitjans i Ubicació (Regla 3-2-1)

Mitjà 1 (Local): NAS, disc dur USB, etc.

Mitjà 2 (Extern): Cloud, Cintes LTO, etc.

Indicar proveïdor: Azure, Google Cloud, AWS, servei local, etc.

Ubicació Fora de Lloc:
On s’emmagatzema la còpia externa i qui és responsable de gestionar-la.

4) Estratègia de Recuperació (RTO/RPO)

Explicar com:

Es garanteix que les dades de Comptabilitat/Clients
→ es recuperen en menys de 4 hores (RTO)
→ amb pèrdua inferior a 4 hores (RPO)

📚 Materials i Recursos

Moodle: 0226 Seguretat Informàtica — RA2.AA3 Còpies

INCIBE: Copias de seguridad. Guía de aproximación para el empresario.

Vídeo Xataka: Backup 3-2-1
