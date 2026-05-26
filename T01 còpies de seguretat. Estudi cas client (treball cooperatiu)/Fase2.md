**FASE 2: GRUPAL**

Després de comparar las tres respostes hem vist que tenim coses semblants com per exemple:

Tots tres coincidim que les dades més importants són les bases de dades, els documents dels clients/usuaris i tot el que afecta al funcionament de l’empresa (facturació, aplicacions, etc.).

També coincidim que no cal fer còpia sencera dels 10 equips clients, només dels documents importants si en tenen.

Sobre la periodicitat: un de nosaltres proposa un calendari diari/setmanal/mensual, i l’altre una còpia incremental diaria.

PROPOSTA UNIFICADA:

| Element | Proposta dels tres  | Justificació  |
| :---- | :---- | :---- |
| Dades Crítiques |  \- Bases de dades \- Documents dels clients/usuaris \- Facturació i comptabilitat \- Aplicacions del sistema \- Logs del servidor | Són les dades que l’empresa necessita sí o sí per funcionar. Si es perden, l’empresa no pot treballar, pot perdre diners o clients. |
| Periodicitat (BD) | \- Diària \- Setmanal \- Mensual | Ens assegura tenir còpies recents (diàries) i punts de restauració més segurs (setmanals i mensuals). |
| Tipus de Còpia (BD) | \- **Diària:** Incremental \- **Setmanal:** Diferencial \- **Mensual:** Completa | La incremental és ràpida i còmoda. La diferencial dona més seguretat a la setmana. La completa mensual deixa una còpia que ho té tot. |
| Mitjà 1 (Local) | NAS | Serveix per fer les còpies diàries i setmanals. És ràpid, segur i sempre encès dins l’empresa. |
| Mitjà 2 (Local / Recanvi) | Disc dur extern | Per guardar la còpia completa mensual i tenir un suport físic extra en cas de fallada del NAS. |
| Mitjà 3 (Extern / Fora de l’empresa) | cloud | És la còpia “fora de lloc”. Protegeix contra incendis, robatoris, inundacions, etc. Fa que complim la regla 3-2-1. |

**RESULTAT FINAL DEL 3-2-:**

**3 còpies**:

NAS (diària i setmanal)

Disc dur extern (mensual)

Cloud (còpia externa)

**2 tipus de suports diferents**:

NAS \+ Disc dur extern \+ Cloud

**1 còpia fora de l’empresa**:

Cloud

