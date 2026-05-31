# 📋 Gestion des Fiches d'Instructions — Application Web

> Projet de Fin d'Études — Licence en Sciences de l'Informatique (Génie Logiciel et Système d'Information)  
> Faculté des Sciences de Tunis — Université de Tunis El Manar  
> Année Universitaire : 2024–2025

---

## 📝 Description

Application web centralisée développée pour **Sagemcom** permettant la digitalisation et la gestion complète des fiches d'instructions de production. Le système remplace un processus entièrement basé sur des documents papier par une solution numérique moderne, sécurisée et traçable.

Les fiches d'instructions guident les techniciens à chaque étape du processus de fabrication. L'application automatise leur cycle de vie : création, workflow d'approbation multi-niveaux, consultation via QR Code, historique des modifications, et tableau de bord analytique.

---

## 👥 Équipe

| Nom | Rôle |
|---|---|
| Ranim Abdellatif | Développeuse |
| Ranim Satouri | Développeuse |

**Encadrant académique :** Mme Naama Amdouni  
**Encadrant professionnel :** M. Mohamed Hedi Zommiti (Sagemcom)

---

## ✨ Fonctionnalités principales

### Sprint 1 — Authentification & Gestion des utilisateurs
- Authentification sécurisée
- Gestion des groupes et des rôles (RBAC)
- Gestion des comptes utilisateurs
- Gestion du profil et du mot de passe

### Sprint 2 — Référentiel de production
- Gestion des zones de production
- Gestion des familles de produits
- Gestion des produits
- Gestion des lignes de production
- Gestion des opérations

### Sprint 3 — Gestion des fiches d'instructions
- Création et modification de fiches d'instructions (associées à une zone, une ligne ou une opération)
- Workflow d'approbation automatisé (multi-niveaux)
- Rejet avec justification
- Consultation des fiches via **QR Code** (accès direct en atelier)
- Fiche du poste AQL (Assurance Qualité Ligne)

### Sprint 4 — Analytique & Outils avancés
- **Tableau de bord Power BI** avec KPIs de production
- Historique détaillé des fiches d'instructions
- Historique des actions utilisateurs
- Recherche avancée dans les fichiers PDF
- Correction grammaticale automatique des commentaires de rejet (via LLM)

---

## 🏗️ Architecture

L'application suit une architecture **3-tiers** :

```
┌─────────────────────────────────────────┐
│         Frontend (Angular)              │
│  Interface web SPA — Architecture MVVM  │
└────────────────┬────────────────────────┘
                 │ HTTP / REST API
┌────────────────┴────────────────────────┐
│         Backend principal               │
│        Spring Boot (Java)               │
│     Architecture MVC — API REST         │
│   Spring Security · Spring Data · JPA   │
├─────────────────────────────────────────┤
│         Service Flask (Python)          │
│  Recherche PDF · Correction grammaticale│
│         (LLM — conteneur séparé)        │
└────────────────┬────────────────────────┘
                 │
┌────────────────┴────────────────────────┐
│           Base de données               │
│              MySQL                      │
└─────────────────────────────────────────┘
```

---

## 🛠️ Stack technologique

### Frontend
- **Angular** — Framework SPA (Google), TypeScript
- Architecture **MVVM**

### Backend
- **Spring Boot** — Framework Java (VMware)
- **Spring Security** — Gestion des accès et authentification
- **Spring Data / JPA** — Persistance des données
- API **REST** (HTTP)

### Service IA / Python
- **Flask** — Micro-framework Python
- Recherche avancée dans les fichiers PDF
- Correction grammaticale via **LLM** (Large Language Model)

### Base de données
- **MySQL** — SGBDR relationnel (Oracle)

### Analytique
- **Microsoft Power BI** — Tableaux de bord et rapports KPI

### Outils de développement
- **IntelliJ IDEA** — IDE backend Java
- **Git** — Contrôle de version
- **Docker** — Conteneurisation du service Flask
- **UML** — Modélisation (diagrammes de cas d'utilisation, séquence, classes)

---

## 🔄 Méthodologie

Le projet a été développé en suivant la méthodologie agile **Scrum**, organisé en **4 sprints** avec backlog produit, planification des sprints et suivi via diagramme de Gantt.

**Acteurs du système :**
- Technicien (consultation via QR Code)
- Ingénieur Produit Documentation Fabrication (IPDF) — création des fiches
- Ingénieur Qualité Produit (IQP) — approbation
- AQL (Assurance Qualité Ligne)
- Administrateur

---

## 🚀 Lancement du projet

### Prérequis
- Java 17+
- Node.js & Angular CLI
- Python 3.x
- MySQL
- Docker (pour le service Flask)

### Backend (Spring Boot)
```bash
# Configurer la base de données dans application.properties
cd backend
./mvnw spring-boot:run
```

### Frontend (Angular)
```bash
cd frontend
npm install
ng serve
```

### Service Flask (Python)
```bash
cd flask-service
pip install -r requirements.txt
python app.py
# ou via Docker
docker build -t flask-service .
docker run -p 5000:5000 flask-service
```

### Base de données
```sql
-- Créer la base de données MySQL
CREATE DATABASE gestion_fiches;
-- Les tables sont générées automatiquement par Spring Data / JPA
```

---

## 📊 Résultats

L'application permet à Sagemcom de :
- **Éliminer le papier** dans le processus de gestion des fiches d'instructions
- Assurer une **traçabilité complète** des modifications
- Offrir un **accès instantané** aux fiches via QR Code en atelier
- Automatiser le **workflow d'approbation**
- Suivre les **indicateurs de performance** via Power BI
- Réduire les **erreurs** grâce à la correction grammaticale automatique

---


*Projet réalisé dans le cadre du stage de fin d'études chez **Sagemcom**, juin 2025.*
