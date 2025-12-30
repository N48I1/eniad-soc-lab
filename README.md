# 🛡️ SOC XDR & SOAR Lab – ENIADB

## 📌 Description du projet

Ce projet consiste à la **mise en place d’un laboratoire SOC (Security Operations Center)** basé sur des **outils open-source**, permettant la **détection, l’analyse, l’enrichissement et l’automatisation de la réponse aux incidents de sécurité**.

La plateforme combine des capacités **XDR (Extended Detection & Response)** et **SOAR (Security Orchestration, Automation and Response)** afin de sécuriser une salle informatique pédagogique dédiée à la cybersécurité.

---

## 🎯 Objectifs

- Centraliser la **collecte et l’analyse des logs** (SIEM/XDR)
- Détecter des activités malveillantes sur les endpoints
- Gérer le **cycle de vie des incidents** (alertes → cas → investigation)
- Enrichir automatiquement les alertes avec des **sources de Threat Intelligence**
- Automatiser les workflows SOC (SOAR)
- Réduire le temps de détection et de réponse aux incidents

---

## 🧰 Outils & Technologies

### 🔹 Wazuh – SIEM / XDR
- Agents Wazuh installés sur les endpoints Windows et Linux
- Collecte de logs (Syslog, FIM, authentification, vulnérabilités)
- Détection des menaces et génération d’alertes
- Dashboard pour la visualisation SOC

### 🔹 TheHive – Incident Response Platform
- Création et gestion des alertes et des cas
- Suivi des investigations
- Association des IOC, TTP et tâches d’analyse
- Intégration avec Cortex, MISP et Shuffle

### 🔹 Cortex – Analyse & Enrichissement
- Exécution d’analyzers automatiques (IP, hash, URL, domaine)
- Enrichissement des alertes TheHive
- Support des responders (actions automatiques)

### 🔹 MISP – Threat Intelligence
- Partage et consultation des IOC
- Enrichissement via des bases de renseignement sur les menaces
- Corrélation avec les alertes SOC

### 🔹 Shuffle – SOAR
- Orchestration et automatisation des workflows SOC
- Réception des alertes Wazuh via Webhook
- Création automatique de cas dans TheHive
- Intégration d’API externes (ex: Gemini AI)

### 🔹 Services externes
- VirusTotal
- APIs d’IA (Gemini) pour aide à l’investigation

---

## 🏗️ Architecture du Lab

### 🔍 Machines surveillées
- **BR08-01 à BR08-04** (Windows endpoints)
- **server-web-dvwa** (serveur web vulnérable)

### 🔐 Composants SOC
- Wazuh Server
- Shuffle
- TheHive
- Cortex
- MISP

### 🔄 Flux principal
Endpoints → Wazuh → Shuffle → TheHive → Cortex / MISP → Notification Email

---

## ⚙️ Fonctionnement global

1. Un événement suspect est détecté par un agent Wazuh
2. Wazuh génère une alerte
3. L’alerte est envoyée à Shuffle via Webhook
4. Shuffle traite l’alerte et applique un workflow
5. Création automatique d’une alerte / cas dans TheHive
6. Enrichissement avec Cortex et MISP
7. Notification envoyée à l’analyste SOC (email)
8. Investigation et réponse à l’incident

---

## 🧪 Démonstration (Cas pratique)

- Exploitation d’une vulnérabilité sur **DVWA**
- Détection par Wazuh (FIM / logs web)
- Transmission de l’alerte à Shuffle
- Création automatique du cas dans TheHive
- Enrichissement IOC via Cortex / VirusTotal
- Notification SOC
- Analyse et clôture du cas

---

## 📊 Résultats obtenus

- Visibilité complète sur les événements de sécurité
- Réduction du temps de réponse aux incidents
- Automatisation des tâches SOC répétitives
- Utilisation d’outils open-source performants
- Plateforme adaptée à un contexte pédagogique

---

## 🚧 Limites & améliorations futures

- Ajout de nouvelles règles de détection Wazuh
- Enrichissement MISP avancé
- Ajout de playbooks SOAR plus complexes
- Supervision d’un plus grand nombre d’endpoints
- Intégration de réponses automatiques (blocage IP, isolation)

---

## 👨‍💻 Développeurs

- **Nabil El Hilali**  
- **Ilyas Majdoubi**

🎓 Étudiants en cybersécurité – ENIADB  
📅 Année académique : 2024 / 2025

---

## 📜 Licence

Projet académique – usage pédagogique uniquement.

