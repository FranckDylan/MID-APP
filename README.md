# 🏃‍♂️ Marathon International de Douala (MID-APP)

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

## 🏆 Les 5 Disciplines

| Discipline | Distance | Tarif | Participants | Checkpoints |
|------------|----------|-------|--------------|-------------|
| Marathon | 42 km | 15 000 FCFA | ~1 200 | 8 CP |
| Semi-Marathon | 21 km | 10 000 FCFA | ~2 500 | 5 CP |
| Marchathon | 10 km | 7 000 FCFA | ~1 800 | 3 CP |
| Marche Familiale | 3x3 km | 5 000 FCFA | ~1 000 | 2 CP |
| Dernier Kilomètre | 3 km | 3 000 FCFA | ~500 | 1 CP |

## 🚀 Quick Start

### Prérequis

- Node.js 20 LTS
- PostgreSQL 16+
- Redis 7+
- Expo CLI
- Git

### Installation

```bash
# Cloner le repository
git clone https://github.com/Franck-F/MID-APP.git
cd MID-APP

# Installer les dépendances
npm install

# Backend
cd backend
cp .env.example .env
npm install
npx prisma generate
npx prisma migrate dev
npm run start:dev

# Mobile App
cd ../mobile
cp .env.example .env
npm install
npx expo start

# Dashboard
cd ../dashboard
cp .env.example .env
npm install
npm run dev
```

## 📁 Structure du Projet

```
MID-APP/
├── backend/              # API NestJS
│   ├── src/
│   │   ├── auth/        # Authentification
│   │   ├── users/       # Gestion utilisateurs
│   │   ├── disciplines/ # Courses
│   │   ├── orders/      # Commandes
│   │   ├── payments/    # Paiements
│   │   ├── tracking/    # GPS tracking
│   │   ├── checkpoints/ # Points de contrôle
│   │   └── notifications/ # Emails/SMS/Push
│   ├── prisma/          # Schéma DB
│   └── package.json
│
├── mobile/              # App React Native
│   ├── app/
│   │   ├── (auth)/     # Écrans auth
│   │   ├── (tabs)/     # Navigation principale
│   │   ├── registration/ # Inscription
│   │   ├── payment/    # Paiements
│   │   └── tracking/   # Suivi GPS
│   ├── components/     # Composants réutilisables
│   ├── services/       # API clients
│   └── package.json
│
├── dashboard/           # Dashboard Next.js
│   ├── app/
│   │   ├── login/      # Auth admin
│   │   ├── dashboard/  # Vue d'ensemble
│   │   ├── live/       # Tracking temps réel
│   │   ├── participants/ # Gestion participants
│   │   └── payments/   # Finance
│   ├── components/     # Composants UI
│   └── package.json
│
├── docs/               # Documentation
│   ├── api/           # API docs
│   ├── deployment/    # Guides déploiement
│   └── user-guides/   # Manuels utilisateur
│
└── .github/           # CI/CD workflows
```

## 🛠️ Stack Technique

### Backend

- **Framework**: NestJS 10.x
- **Database**: PostgreSQL 16 + PostGIS
- **Cache**: Redis 7.x
- **ORM**: Prisma 5.x
- **WebSockets**: Socket.io
- **Auth**: Passport.js + JWT

### Mobile

- **Framework**: React Native (Expo SDK 51+)
- **Language**: TypeScript 5.3+
- **Navigation**: Expo Router
- **State**: Zustand + TanStack Query
- **Maps**: react-native-maps
- **Location**: expo-location
- **Styling**: NativeWind (Tailwind)

### Dashboard

- **Framework**: Next.js 14.x
- **Styling**: Tailwind CSS + shadcn/ui
- **Maps**: Mapbox GL
- **Charts**: Recharts
- **Real-time**: Socket.io-client

### Paiements

- Orange Money (API OMAPI)
- MTN Mobile Money
- PayPal REST API
- Stripe API

## 🔧 Configuration

### Variables d'Environnement

#### Backend (.env)

```env
DATABASE_URL="postgresql://user:password@localhost:5432/mid_app"
REDIS_URL="redis://localhost:6379"
JWT_SECRET="your-secret-key"
ORANGE_MONEY_API_KEY="..."
MTN_MOMO_API_KEY="..."
PAYPAL_CLIENT_ID="..."
STRIPE_SECRET_KEY="..."
```

#### Mobile (.env)

```env
EXPO_PUBLIC_API_URL="http://localhost:3000"
EXPO_PUBLIC_WS_URL="ws://localhost:3000"
EXPO_PUBLIC_GOOGLE_MAPS_API_KEY="..."
```

#### Dashboard (.env)

```env
NEXT_PUBLIC_API_URL="http://localhost:3000"
NEXT_PUBLIC_MAPBOX_TOKEN="..."
```

## 📱 Fonctionnalités Principales

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
- ✅ Communication de masse

## 🚀 Déploiement

### Infrastructure Recommandée

- **Serveur API**: DigitalOcean Droplet (4vCPU, 8GB RAM)
- **Database**: DigitalOcean Managed PostgreSQL
- **Cache**: DigitalOcean Managed Redis
- **Storage**: DigitalOcean Spaces
- **CDN**: Cloudflare

### CI/CD

GitHub Actions configuré pour:

- Tests automatiques
- Build et déploiement backend
- Build mobile (EAS Build)
- Déploiement dashboard

## 📊 Monitoring

- **Métriques**: Grafana + Prometheus
- **Logs**: Loki
- **Alertes**: PagerDuty
- **Uptime**: UptimeRobot

## 🔒 Sécurité

- JWT avec rotation des tokens
- HTTPS obligatoire (TLS 1.3)
- Rate limiting
- 2FA pour admins
- Conformité RGPD
- PCI-DSS via Stripe

## 📅 Planning

| Phase | Période | Modules |
|-------|---------|---------|
| 1 | Jan-Mar 2025 | Setup, Auth, Paiements |
| 2 | Avr-Jun 2025 | GPS, Maps, Checkpoints |
| 3 | Jul-Sep 2025 | Dashboard, Temps réel |
| 4 | Oct-Déc 2025 | UI/UX, Optimisation |
| 5 | Jan-Mai 2026 | Beta, Production |

## 📄 License

MIT License - voir [LICENSE](LICENSE)

## 👥 Équipe

- **Product Owner**: [À définir]
- **Tech Lead**: [À définir]
- **Développeurs**: [À définir]

## 📞 Contact

- **Email**: <contact@marathon-douala.cm>
- **Website**: <https://marathon-douala.cm>
- **Support**: <support@marathon-douala.cm>

---

**Événement**: Octobre 2026 🇨🇲
**Participants attendus**: ~7 000 personnes
