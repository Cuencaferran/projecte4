🛡️ T03 – Pla de Recuperació davant Desastres: Imatges del Sistema

Client: Muntatges i Serveis Tècnics SL
Objectiu: Elaboració del DRP referent a la restauració ràpida d’equips GNU/Linux (Zorin OS 18)

📘 FASE 1 — Anàlisi i Justificació de la Solució Tècnica

L’objectiu és seleccionar una eina que permeti crear i restaurar imatges completes dels equips Zorin OS 18, assegurant una recuperació ràpida davant robatori, avaria o incident greu.

Es comparen 4 solucions:

2 comercials

2 de comunitat

🧩 Eines comercials
💼 1. Acronis Cyber Protect

Característiques destacades

Imatges completes, incrementals i diferencials.

Restauració sobre maquinari diferent (Universal Restore).

Xifrat, verificació i control d’integritat.

Console centralitzada ideal per empreses.

Preu aproximat

A partir de 69 €/any per equip.

Punts forts

Extremadament estable i robust.

Gran suport tècnic i automatització.

Punts febles

Preu elevat.

Pot ser excessiu per entorns petits.

💼 2. Clone Manager (Eines empresarials de clonació, ex: SmartDeploy / CloneDeploy Enterprise)

Característiques destacades

Imatges personalitzades amb aplicacions i configuracions.

Desplegament ràpid a múltiples equips.

Compatible amb GNU/Linux i Windows.

Gestió centralitzada via servidor.

Preu aproximat

Entre 400–600 € anuals per organització petita.

Punts forts

Molt orientat a entorns corporatius.

Automatització del desplegament.

Punts febles

Infraestructura més complexa.

Cost per sobre de les opcions comunitàries.

🧩 Eines de comunitat
🌱 3. Clonezilla

Característiques destacades

Imatges completes i particionals.

Rapidíssim, molt eficient i lleuger.

Gratuït i de codi obert.

Replicació massiva via Clonezilla Server.

Preu

Gratuït

Punts forts

Rendiment altíssim.

Extremadament fiable.

Punts febles

Interfície poc intuïtiva.

No apte per usuaris poc tècnics.

🌱 4. Rescuezilla

Característiques destacades

Entorn gràfic sobre Ubuntu.

Compatible amb imatges Clonezilla.

Restauració i creació de imatges molt simples.

Suport per a discs externs, xarxa, i múltiples formats.

Preu

Gratuït

Punts forts

Ús molt amigable.

Ideal per equips de suport no experts.

Punts febles

Menys opcions avançades que Acronis.

Menys velocitat que Clonezilla en clonacions massives.

🏆 Proposta recomanada
Recomanació: Rescuezilla

Justificació

El client necessita rapidesa, no complexitat.

La plantilla tècnica ha de poder restaurar equips fàcilment, sense formació avançada.

És gratuït, eliminant costos recurrents del DRP.

És totalment compatible amb Zorin OS 18.

Permet crear i restaurar imatges amb interfície gràfica clara, minimitzant errors.

Per tant, Rescuezilla és la solució amb millor relació simplicitat + fiabilitat + cost zero, ideal per aquest cas.

🛠️ FASE 2 — Guia Tècnica (Manual Operatiu) amb Rescuezilla

A continuació es documenta el procés que el personal de manteniment ha de seguir:

Crear una imatge completa del sistema Zorin OS 18

Restaurar-la sobre un equip net (disc buit)

Aquest procés s’ha realitzat sobre una màquina virtual OVA proporcionada pel client.

📀 1. Crear una imatge completa del sistema amb Rescuezilla
🔧 1.1 Preparatius

Descarregar ISO de Rescuezilla:
👉 https://rescuezilla.com

Crear una màquina virtual amb:

Mateixes característiques que la màquina original.

Carregar la ISO a la VM (o arrencar per USB si és físic).

🚀 1.2 Arrencar Rescuezilla

Al menú d’arrencada → seleccionar Rescuezilla

Esperar a què carregui l’entorn gràfic.

📸 1.3 Crear la imatge del disc

Obrir Rescue → “Backup”.

Seleccionar el disc origen (el disc on hi ha Zorin OS instal·lat).

Seleccionar el destí:

Disc extern USB

Carpeta compartida

Un segon disc virtual

Introduir:

Nom de la imatge

Carpeta on guardar-la

Confirmar els paràmetres → Start Backup

⏳ 1.4 Procés i verificació

Rescuezilla mostrarà una barra de progrés.

En finalitzar, es recomana marcatge de:

✔️ Verificació de la imatge

✔️ Integritat del backup

La imatge contindrà tot l’equip: sistema operatiu, configuracions, programes i dades.

💾 2. Restauració de la imatge

Aquesta fase simula la reposició d’un equip nou després d’un desastre.

🌱 2.1 Preparar la màquina de destinació

Crear una nova VM idèntica a l’original:

Mateixa RAM

Mateix nombre de CPU

Mateixa mida de disc

El disc ha d’estar buit (sense OS).

🚀 2.2 Arrencar Rescuezilla a la màquina neta

Afegir la ISO de Rescuezilla.

Arrencar → seleccionar Rescuezilla (Default).

📂 2.3 Seleccionar restauració

Restore

Seleccionar la imatge prèviament creada

Seleccionar:

Disc destí (el disc buit)

Confirmar i iniciar Start Restore

⏳ 2.4 Procés de clonació

La imatge serà escrita exactament com estava.

Un cop finalitzada → Reboot.

🎉 2.5 Resultat

El sistema arrencarà com si fos l’equip original:

Mateixes aplicacions

Mateixes configuracions

Mateixes dades

Mateix estat general del sistema

Temps total estimat de restauració: 10–15 minuts, segons mida del disc.

✔️ Conclusió

La solució proposada (Rescuezilla) permet:

Recuperar equips en minuts

Reduir el temps de parada del personal

Garantir la continuïtat del negoci

Simplificar enormement el DRP

Evitar costos en llicències

És la solució òptima per al cas de Muntatges i Serveis Tècnics SL.
