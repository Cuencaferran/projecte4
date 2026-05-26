**Document Final (Fase 3\)**

El grup ha de generar un document amb els següents punts resolts:

1\)      Dades Objecte de Còpia

Quines dades es copien i amb quina freqüència (separant Servidor/Clients i crítiques/no crítiques).

| Tipus de dada | Descripció | Crítica? | Freqüència |
| ----- | ----- | ----- | ----- |
| **Base de Dades Comptabilitat** | Informació financera i comptable | **Sí** | **Cada 4 h (incremental)** \+ diària completa |
| **Base de Dades Clients/CRM** | Dades de clients, comandes, contractes | **Sí** | **Cada 4 h (incremental)** \+ diària completa |
| **Fitxers de projectes** | Documents interns, informes, arxius compartits | No | 1 còpia diària |
| **Configuracions del servidor** | Sistemes, usuaris, polítiques | Sí | 1 còpia diària |
| **Sistema complet (imatge)** | Backup complet del servidor | No | 1 còpia setmanal |

### **Equips Clients (PCs d’oficina)**

| Tipus de dada | Descripció | Crítica? | Freqüència |
| ----- | ----- | ----- | ----- |
| **Documents d’usuari** | Word, Excel, PDF | No (sincronitzats al servidor) | 1 còpia diària |
| **Configuracions d’equip** | Perfil Windows, aplicacions | No | 1 còpia setmanal |
| **Emails (si local)** | PST/OST | Sí | 1 còpia diària (si no es fa al servidor) |

2\)      Cronograma Setmanal Detallat 

| Dia | Dades | Tipus de Còpia | Mitjà |
| ----- | ----- | ----- | ----- |
| **Dilluns** | BD Comptabilitat i Clients | Incremental (cada 4 h) | NAS Local |
|  | Fitxers compartits | Completa | NAS Local |
|  | Configuració servidors | Completa | NAS Local |
| **Dimarts** | BD Comptabilitat i Clients | Incremental (cada 4 h) | NAS Local |
|  | Fitxers PC usuaris | Completa | NAS Local |
| **Dimecres** | BD Comptabilitat i Clients | Incremental (cada 4 h) | NAS Local |
|  | Fitxers compartits | Incremental | NAS Local |
| **Dijous** | BD Comptabilitat i Clients | Incremental (cada 4 h) | NAS Local |
|  | Configuracions servidors | Incremental | NAS Local |
| **Divendres** | BD Comptabilitat i Clients | Incremental (cada 4 h) | NAS Local |
|  | Fitxers compartits | Completa | NAS Local |
| **Dissabte** | Imatge completa del servidor | Completa | NAS \+ Cloud |
|  | Replicació setmanal al cloud | Completa | Cloud extern |
| **Diumenge** | Cap còpia operativa | — | Tasques de manteniment/validació |

3\)      Elecció de Mitjans i Ubicació (Regla 3-2-1)

### **Regla 3-2-1 aplicada**

**3 còpies** de cada dada crítica (Producció \+ NAS \+ Cloud)

**2 tipus de mitjà** (Disc/NAS \+ Cloud)

**1 còpia fora de lloc**

### **Mitjà 1 – Local**

**Tipus:** NAS en xarxa (RAID 5 o RAID 6\)

**Model recomanat:** Synology DS923+ o similar

**Freqüència:** Totes les còpies diàries i incrementals

### **Mitjà 2 – Extern**

**Tipus:** Emmagatzematge Cloud xifrat

**Proveïdor:** **Azure Backup** o **Google Cloud Storage Nearline**

**Freqüència:** Còpia completa setmanal \+ còpia incremental diària només de dades crítiques

### **Ubicació Fora de Lloc**

**Entorn:** Cloud públic (redundància multi-region)

**Xifrat:** AES-256 \+ control d’accés MFA

**Responsable:** Administrador TIC / Responsable de Sistemes

**Validació:** Test de restauració mensual documentat

## **Estratègia de Recuperació (RTO / RPO)**

### **Objectius**

**RPO \= 4 hores**  
  No es poden perdre més de 4 h de dades

**RTO \= 4 hores**  
  El sistema ha d’estar restaurat en menys de 4 h

### **Com es garanteix l’RPO (4 hores)**

### 

###  Backups **incrementals cada 4 hores** de BD Comptabilitat i Clients  Sistema de registre continu Replicació del NAS local al cloud diàriament

### **Com es garanteix l’RTO (4 hores)**

###  Imatge completa del servidor al NAS → restauració ràpida amb sistema de **bare-metal restore**

###  Disponibilitat d’un servidor de substitució (físic o virtual) preconfigura

###   Procés automatitzat per restaurar BDs i serveis essencials   

### Procediment documentat \+ proves mensuals de recuperació

### **Temps estimats**

Restauració imatge servidor → 1 hora

Restaura BD Comptabilitat/Clients → 30 minuts

Validació i reengegada serveis → 30-60 minuts  
 ➡ **Total ≤ 4 hores (compliment garantit)**

