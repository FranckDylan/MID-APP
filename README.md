# Marathon International de Douala (MID-APP)

![Marathon](https://img.shields.io/badge/Event-Mai%202026-blue)
![Participants](https://img.shields.io/badge/Participants-~7000-green)
![Disciplines](https://img.shields.io/badge/Disciplines-5-orange)

Application complète de gestion du Marathon International de Douala - De l'inscription en ligne au suivi GPS en temps réel.

## 📋 Vue d'Ensemble

Plateforme complète comprenant:

- **Backend API** (NestJS + PostgreSQL + Redis)
- **Application Mobile** (React Native + Expo)
- **Dashboard Web** (Next.js)
- **Intégrations Paiement** (Orange Money, MTN MoMo, PayPal, Stripe)
- **Tracking GPS Temps Réel**

## Les 5 Disciplines

| Discipline | Distance | Tarif | Participants | Checkpoints |
|------------|----------|-------|--------------|-------------|
| Marathon | 42 km | 15 000 FCFA | ~1 200 | 8 CP |
| Semi-Marathon | 21 km | 10 000 FCFA | ~2 500 | 5 CP |
| Marchathon | 10 km | 7 000 FCFA | ~1 800 | 3 CP |
| Marche Familiale | 3x3 km | 5 000 FCFA | ~1 000 | 2 CP |
| Dernier Kilomètre | 3 km | 3 000 FCFA | ~500 | 1 CP |


```bash
# Cloner le repository
git clone https://github.com/Franck-F/MID-APP.git
cd MID-APP

# Installer les dépendances
npm install

## Fonctionnalités Principales

### Application Mobile Participant

- ✅ Inscription avec paiement en ligne
- ✅ Dossard digital avec QR Code
- ✅ Tracking GPS en temps réel
- ✅ Statistiques live (distance, allure, temps)
- ✅ Détection automatique checkpoints
- ✅ Classements temps réel
- ✅ Certificat de participation
- ✅ Partage sur réseaux sociaux

### Dashboard Organisateurs

- ✅ Carte temps réel de tous les coureurs
- ✅ Gestion des participants
- ✅ Monitoring des checkpoints
- ✅ Alertes et incidents
- ✅ Statistiques et rapports
- ✅ Gestion financière

##  License

MIT License - voir [LICENSE](LICENSE)
