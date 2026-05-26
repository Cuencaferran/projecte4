# T03: Pla de Recuperació davant Desastres — Imatges del Sistema

## 📝 Descripció del Projecte
Aquest projecte neix de la necessitat de dissenyar i executar part d'un **Pla de Contingència i Continuïtat del Negoci**, concretament el **Pla de Recuperació davant Desastres (DRP - Disaster Recovery Plan)** per a un client. 

L'objectiu principal és garantir que els treballadors puguin disposar de forma ràpida dels seus equips de treball en cas de robatori, avaria o catàstrofe, minimitzant el temps d'inactivitat. Atès que el temps de posada en marxa és crític, es descarta la instal·lació clàssica (sistema operatiu des de zero + configuracions + aplicacions) i s'opta per la **creació i restauració d'imatges de sistema**.

> 💻 **Entorn del client:** Tots els equips de l'empresa utilitzen la distribució **Zorin OS 18** amb un conjunt d'aplicacions i configuracions ja predefinides.

---

## ⏳ Fases del Projecte

### 🔍 Fase 1: Anàlisi i Justificació de la Solució Tècnica
En aquesta fase es realitzarà una investigació i comparativa de mercat per seleccionar l'eina ideal per a la clonació i restauració de discs. 

#### Taula Comparativa d'Eines
Cal triar i analitzar **2 solucions comercials** i **2 de la comunitat (Open Source)**. La comparativa s'ha de centrar en les característiques clau per al cas de l'empresa:

| Tipus de Solució | Nom del Producte | Característiques Destacades | Preu / Llicència |
| :--- | :--- | :--- | :--- |
| **Comercial 1** | *[Completar amb producte, ex: Acronis Cyber Protect]* | *[Ex: Gestió centralitzada, còpies al núvol]* | *[Preu per llicència/any]* |
| **Comercial 2** | *[Completar amb producte, ex: Macrium Reflect]* | *[Ex: Rapid Delta Restore, suport empresarial]* | *[Preu per endpoint]* |
| **Comunitat 1** | *[Completar amb producte, ex: Clonezilla]* | *[Ex: Molt lleuger, suporta moolts sistemes de fitxers]* | Gratis / Open Source |
| **Comunitat 2** | *[Completar amb producte, ex: Rescuezilla]* | *[Ex: Interfície gràfica intuïtiva, compatible amb Clonezilla]* | Gratis / Open Source |

#### 🎯 Solució Proposada i Justificació
*[En aquest apartat s'ha d'incloure la justificació raonada de l'eina escollida per a l'entorn de producció final del client, basant-se en els costos, la facilitat d'ús pel personal tècnic i la compatibilitat amb Zorin OS 18].*

---

### 🛠️ Fase 2: Guia d'Ús Tècnica (Manual Operatiu)
Com que es tracta d'una **Prova de Concepte (PoC)** i la proposta final encara s'ha d'aprovar, s'utilitzarà **Rescuezilla** per a la realització d'aquesta guia. 

El manual ha de guiar pas a pas el personal de manteniment a través dels dos processos clau utilitzant la màquina virtual (OVA) proveïda:

#### 1. Creació d'una Imatge Completa del Sistema
* **Pas 1:** Configuració del boot de la màquina virtual amb la ISO de Rescuezilla.
* **Pas 2:** Selecció de l'opció de *Backup* (Còpia de seguretat).
* **Pas 3:** Identificació del disc origen (Zorin OS 18) i destí (unitat de xarxa o disc extern).
* *[Afegir captures de pantalla significatives del procés]*

#### 2. Restauració de la Imatge sobre un Sistema Net
* **Pas 1:** Inici d'una màquina virtual idèntica buida (sense SO instal·lat) des de la ISO de Rescuezilla.
* **Pas 2:** Selecció de l'opció de *Restore* (Restauració).
* **Pas 3:** Localització de la imatge creada al punt anterior i selecció del disc destí.
* *[Afegir captures de pantalla significatives del procés]*

---

## 🗂️ Informació de l'Entrega
* **Tipus de tasca:** Individual.
* **Requisit de qualitat:** Documentació acurada, capturant només els passos realment significatius i explicant el procediment de forma entenedora per al personal de suport.

## 🔗 Materials i Links de Suport
* [INCIBE: ¿Ya tienes tu Plan de Recuperación ante Desastres?](https://www.incibe.es/empresas/blog/tienes-tu-plan-recuperacion-desastres)
* [Pàgina oficial de Rescuezilla](https://rescuezilla.com/)