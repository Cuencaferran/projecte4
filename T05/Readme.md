# 🛡️ **T05: Accés Remot — Connexió via SSH**  
**Guia Interna per a Nous Tècnics (PoC corporativa)**

---

## 📘 **Introducció**
L’accés remot segur és una peça essencial de la nostra operativa a la consultora. Els servidors dels clients (i els nostres interns) es troben en CPDs o al núvol, i l'accés físic és excepcional.  

Per aquest motiu utilitzem **SSH (Secure Shell)**, l’estàndard industrial per administrar màquines Linux de manera segura, xifrada i eficient.

Aquesta guia servirà com a base de coneixement per als futurs becaris i tècnics que s’incorporin a l’equip. L’objectiu és disposar d’un document clar, complet i professional que els permeti operar des del primer dia.

---

# 🎯 **Objectiu de la PoC**
Crear una guia impecable sobre com realitzar connexions SSH entre els entorns que utilitzem habitualment:

- 🐧 **Clients Linux** (terminal nativa)
- 🪟 **Clients Windows** (PowerShell o Windows Terminal)

Aquest document s'ha elaborat seguint les activitats i requisits de la **Pràctica SSH** (Moodle 0227 Serveis de Xarxa · UD4.AA2).

---

# 🧰 **Eines i Recursos**
- **Dues màquines virtuals** (Linux/Linux, Linux/Windows o Windows/Linux)
- Enllaç de suport: *Vídeo — SSH amb clau pública/privada*
- Fitxa de pràctica Moodle: *UD4.AA2 Pràctica SSH*

---

# 🔐 **1. Fonaments d’SSH**
SSH permet:
- Connexions remotes segures.
- Transferència de fitxers xifrada.
- Autenticació mitjançant contrasenya o claus pública/privada.
- Administració completa del sistema remot.

Format general de connexió:
