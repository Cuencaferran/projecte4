# T01: DRP — Còpies de Seguretat. Estudi de Cas Client

## 📝 Breu Descripció

Un dels pilars fonamentals del **Pla de Recuperació davant de Desastres (DRP)** en la consultoria de sistemes és el disseny i execució d'una política robusta de còpies de seguretat. Aquesta pràctica es basa en un cas real: l'empresa **"Muntatges i Serveis Tècnics SL"**, una petita organització d'instal·lació i manteniment d'equips industrials. 

L'objectiu és aconseguir el consens tècnic a través d'una dinàmica de treball cooperatiu (*Individual ➔ Parelles ➔ Grup*) per blindar les dades crítiques de la companyia complint estrictament amb mètriques de negoci com el **RTO** i el **RPO**.

---

## 🏬 Auditoria de la Infraestructura i Requisits del Client

### 🖥️ 1. Actius d'Informació (Servidor Ubuntu)
* **Documents de Projectes:** Plànols i especificacions tècniques (**300 GB**, creixement moderat).
* **Bases de Dades (BD):** Gestió de Comptabilitat i Clients (**20 GB**, crític, canvi constant).
* **Carpetes Personals:** Treball diari dels usuaris (**100 GB**).
* **Clients Integrats:** 10 Equips (Windows 10/11) amb desar temporal d'informes a la carpeta local *Documents*.
* **Xarxa:** Fibra òptica de **600 Mbps simètrics**.

### ⏱️ 2. Llindars de Tolerància (Mètriques DRP)
* **RTO (Recovery Time Objective):** Les dades de Comptabilitat/Clients han de reincorporar-se a la producció en **menys de 4 hores**.
* **RPO (Recovery Point Objective):** Màxim 24 hores de pèrdua admesa en dades generals, però limitat a un màxim estricte de **4 hores** en Comptabilitat/Clients.
* **Retenció legal/operativa:** Historial mínim d'**1 mes** garantit.

---

## 🔄 Fases de la Dinàmica Cooperativa

### 👤 Fase 1: Treball Individual
Cada membre de l'equip analitza de forma aïllada el cas de negoci per respondre tres preguntes clau de diagnòstic:
1. **Què copiar? (Priorització):** Identificació i justificació dels actius més crítics. Decisió sobre l'exclusió o inclusió de còpies en els 10 clients Windows.
2. **Periodicitat i Tipus:** Proposta inicial d'un esquema setmanal utilitzant variants de còpies (Completa, Incremental o Diferencial) que s'ajustin a les finestres de temps del RPO.
3. **Mitjans i Ubicació:** Preselecció del suport (NAS, Cloud, Discs Externs, LTO) aplicant les nocions bàsiques de la protecció de dades.

### 👥 Fase 2: Treball per Parelles
Espai de discussió, contrast