# CanineAI Client 🐾

[![React](https://img.shields.io/badge/React-19.2-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev/)
[![Vite](https://img.shields.io/badge/Vite-7.3-646CFF?style=for-the-badge&logo=vite&logoColor=white)](https://vitejs.dev/)
[![Tailwind CSS](https://img.shields.io/badge/TailwindCSS-3.4-38B2AC?style=for-the-badge&logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![React Router](https://img.shields.io/badge/React_Router-v7-CA4245?style=for-the-badge&logo=reactrouter&logoColor=white)](https://reactrouter.com/)
[![Axios](https://img.shields.io/badge/Axios-HTTP_Client-5A29E4?style=for-the-badge&logo=axios&logoColor=white)](https://axios-http.com/)
[![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?style=for-the-badge&logo=docker&logoColor=white)](https://www.docker.com/)

**CanineAI Client** is the responsive, modern web application for the CanineAI platform. Built with **React 19**, **Vite**, and **Tailwind CSS**, it provides dog owners with an intuitive interface to manage multiple pet profiles, explore an interactive canine disease encyclopedia, select symptoms, and receive machine learning-powered health assessments and differential diagnoses.

---

## 🏗️ Application Architecture

```text
       +-------------------------------------------------+
       |              CanineAI React 19 Client           |
       |  +-------------------------------------------+  |
       |  |  React Router v7 Layouts & Protected Gates|  |
       |  +-------------------------------------------+  |
       |  |  AuthContext (JWT State & User Profile)   |  |
       |  +-------------------------------------------+  |
       |  |  Pages: Landing, Dashboard, Dogs, AI Care |  |
       |  +-------------------------------------------+  |
       |  |  Axios HTTP Interceptor (Cookie & Header) |  |
       +-----------+-------------------------+-----------+
                   |                         |
                   ▼                         ▼
          CanineAI Spring API         Cloudinary CDN
         (Endpoints / Predict)     (Pet & User Avatars)
```

---

## ✨ Key Features

- **🐕 Multi-Dog Profile Hub**: Register, edit, and track multiple dogs with details like breed, age, gender, weight, profile pictures, and clinical histories.
- **🧠 Interactive AI Symptom Checker**: Select observed symptoms through an categorized tag cloud to receive real-time disease predictions with confidence scores and top-3 differential diagnoses.
- **📜 Diagnosis History & Records**: Chronological audit log of all previous symptom assessments, predictions, and recommendations per dog.
- **📚 Canine Disease Encyclopedia**: Comprehensive health library with dynamic search, severity filtering, detailed symptoms, causes, prevention advice, and veterinarian tips.
- **🔐 Secure Authentication**: Protected routes with token validation, session persistence, seamless login/registration, and password reset flows.
- **📸 Cloud Media Integration**: One-click photo upload for pet avatars with client-side preview and Cloudinary CDN optimization.
- **📱 Fully Responsive Experience**: Mobile-first design optimized for phones, tablets, and desktop displays with smooth transitions.

---

## 🛠️ Tech Stack

| Layer | Technology | Purpose |
| :--- | :--- | :--- |
| **Frontend Core** | React 19.2 | Component-driven UI and state synchronization |
| **Build Tool** | Vite 7.3 | Ultra-fast HMR and optimized production bundles |
| **Routing** | React Router DOM v7 | Declarative nested routing, layouts, and route guards |
| **Styling** | Tailwind CSS 3.4 | Utility-first responsive design system |
| **Networking** | Axios | Interceptor-enabled REST client with credentials |
| **Media CDN** | Cloudinary | Cloud-based image upload and asset transformation |
| **Containerization** | Docker & Nginx | Production multi-stage build and static hosting |

---

## 📁 Project Directory Structure

```text
canine-ai-client/
├── public/                    # Static assets and icons
├── src/
│   ├── components/
│   │   ├── common/            # Navbar, Footer, ScrollToTop, DynamicInfoCard
│   │   ├── dashboard/         # DashboardLayout, SideMenu
│   │   ├── disease-detail/    # Causes, Overview, Prevention, SymptomsGrid
│   │   └── diseases/          # DiseaseCard, DiseaseFilters, DiseasesGrid
│   ├── context/
│   │   └── AuthContext.jsx    # Global user session & authentication state
│   ├── pages/
│   │   ├── dashboard/         # AddDog, EditDog, MyDogs, PredictDisease, History
│   │   ├── AboutPage.jsx      # About platform & veterinary disclaimer
│   │   ├── DiseaseDetailPage.jsx # Comprehensive illness view
│   │   ├── DiseasesPage.jsx   # Searchable disease catalog
│   │   ├── FAQsPage.jsx       # Frequently asked questions
│   │   ├── LandingPage.jsx    # Hero section, feature teasers, CTA
│   │   ├── LoginPage.jsx      # Account sign in
│   │   └── SignupPage.jsx     # New account registration
│   ├── services/              # API Clients (Auth, Dog, Disease, Symptom, Predict)
│   │   └── httpClient.js      # Base Axios instance with withCredentials
│   ├── utils/                 # Response parser and Cloudinary upload helpers
│   ├── App.jsx                # Route definitions and provider wiring
│   ├── main.jsx               # React DOM root entry
│   └── index.css              # Tailwind base, components, and utilities
├── .env.example               # Template environment configuration
├── Dockerfile                 # Multi-stage container build
├── package.json               # Dependencies and scripts
├── tailwind.config.js         # Tailwind styling tokens
└── vite.config.js             # Vite configuration
```

---

## 🚦 Application Routes

| Path | Access Level | Description |
| :--- | :--- | :--- |
| `/` | Public | Homepage showcasing AI features & disease library |
| `/diseases` | Public | Searchable directory of canine health conditions |
| `/diseases/:id` | Public | Clinical breakdown of a specific illness |
| `/login` / `/signup` | Public | Account authentication and registration |
| `/dashboard` | Protected | Owner dashboard overview & pet summary |
| `/dashboard/my-dogs` | Protected | Pet directory with actions to add or view dogs |
| `/dashboard/add-dog` | Protected | New pet registration form with photo upload |
| `/dashboard/predict` | Protected | Interactive AI symptom checker & diagnostics |
| `/dashboard/history` | Protected | Past prediction history and veterinary summaries |
| `/dashboard/profile` | Protected | Manage owner account settings and password |

---

## ⚙️ Environment Configuration

Create a `.env` file in the root directory:

```bash
cp .env.example .env
```

| Key | Description | Example Value |
| :--- | :--- | :--- |
| `VITE_API_BASE_URL` | CanineAI Spring Boot backend URL | `http://localhost:8080/api` |
| `VITE_CLOUDINARY_CLOUD_NAME` | Cloudinary account cloud name | `your-cloud-name` |
| `VITE_CLOUDINARY_UPLOAD_PRESET` | Unsigned upload preset for pet photos | `canine_ai_presets` |

---

## 🚀 Getting Started

### Prerequisites
- **Node.js**: v18.0.0 or higher (v20+ recommended)
- **Package Manager**: `npm`, `pnpm`, or `yarn`

### 1. Installation
```bash
git clone https://github.com/gitApurv/canine-ai-client.git
cd canine-ai-client
npm install
```

### 2. Run Development Server
```bash
npm run dev
```
The app will be accessible at `http://localhost:5173`.

### 3. Build for Production
```bash
npm run build
npm run preview
```

---

## 🐳 Docker Deployment

Build and run using Docker:

```bash
# Build the image
docker build -t canine-ai-client:latest .

# Run the container on port 80
docker run -d -p 80:80 --name canine-ai-client canine-ai-client:latest
```

---

## 👨‍💻 Author

**Apurv**
- GitHub: [@gitApurv](https://github.com/gitApurv)
