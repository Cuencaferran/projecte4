# FASE 2: Treball Grupal
🗣️ Comparació de les respostes

Després de comparar les tres respostes individuals hem vist que compartim força idees en comú:

Tots tres coincidim que les dades més importants són:

Bases de dades

Documents dels clients/usuaris

Facturació i comptabilitat

Aplicacions del sistema

Logs del servidor

També coincidim que no cal fer còpia sencera dels 10 equips clients, només dels documents realment importants que puguin guardar.

En la periodicitat, un proposava calendari diari/setmanal/mensual, i un altre una còpia incremental diària.
→ Hem unificat les dues idees.

📌 Proposta Unificada
Element	Proposta dels tres	Justificació
Dades Crítiques	- Bases de dades
- Documents dels clients/usuaris
- Facturació i comptabilitat
- Aplicacions del sistema
- Logs del servidor	Són essencials per al funcionament de l’empresa. Si es perden, es poden perdre diners, clients o parar la feina.
Periodicitat (BD)	- Diària
- Setmanal
- Mensual	Ens dona còpies recents i punts de restauració segurs al llarg de la setmana i del mes.
Tipus de Còpia (BD)	- Diària: Incremental
- Setmanal: Diferencial
- Mensual: Completa	La incremental és ràpida, la diferencial és més segura setmanalment, i la completa guarda tota la info mensualment.
Mitjà 1 (Local)	NAS	Ideal per a còpies diàries i setmanals: ràpid, segur i sempre disponible.
Mitjà 2 (Local / Recanvi)	Disc dur extern	Serveix per guardar còpies mensuals i tenir un suport extra en cas de fallada.
Mitjà 3 (Extern / Fora de l’empresa)	Cloud	Assegura una còpia fora de l’empresa per protegir de robatoris, incendis o desastres. Compleix la regla 3-2-1.
🔒 Resultat Final del Model 3-2-1
3 Còpies:

NAS → còpia diària i setmanal

Disc dur extern → còpia mensual

Cloud → còpia externa

2 Tipus de Suports Diferents:

NAS

Disc dur extern

Cloud

1 Còpia fora de l’empresa:

Cloud
