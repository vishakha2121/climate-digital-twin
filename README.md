<div align="center">

# 🌍 Climate Digital Twin

### Multi-Agent AI Simulation Network for Earth's Climate

**5 AI Agents · Physics-Based Simulation · Gemini-Powered Predictions**

[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-009688?style=for-the-badge&logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com)
[![React](https://img.shields.io/badge/React-18+-61DAFB?style=for-the-badge&logo=react&logoColor=black)](https://react.dev)
[![TailwindCSS](https://img.shields.io/badge/TailwindCSS-3.0+-06B6D4?style=for-the-badge&logo=tailwindcss&logoColor=white)](https://tailwindcss.com)
[![Gemini](https://img.shields.io/badge/Gemini-AI-4285F4?style=for-the-badge&logo=google&logoColor=white)](https://ai.google.dev)
[![SQLite](https://img.shields.io/badge/SQLite-3-003B57?style=for-the-badge&logo=sqlite&logoColor=white)](https://sqlite.org)
[![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)](LICENSE)

*A multi-agent AI digital twin that simulates Earth's oceans, forests, atmosphere, agriculture, and cities to predict climate change using physics-based models and Google Gemini AI.*

[Overview](#-overview) · [Features](#-features) · [Architecture](#-architecture) · [Tech Stack](#-tech-stack) · [Setup](#-installation--setup) · [API](#-api-endpoints) · [Screenshots](#-screenshots)

</div>

---

## 📖 Overview

**Climate Digital Twin** is an advanced multi-agent AI simulation platform that creates a **living digital replica of Earth's climate system**. Instead of relying on a single monolithic model, the system uses **five specialized AI agents** — each simulating a different domain of our planet — that interact with each other through a central physics-based orchestrator.

The predictions and insights are generated using **Google Gemini AI**, making the system capable of natural-language reasoning about climate scenarios.

> **Assignment Category:** Advanced · Physics AI · Digital Twin · Foundation Models

---

## 🎯 Problem Statement

Climate change is a **multi-domain problem**. Oceans, forests, atmosphere, agriculture, and cities all influence each other in complex, non-linear ways:

- 🌊 **Oceans** absorb CO₂ and heat → affect **atmosphere**
- 🌳 **Forests** capture carbon → affected by **city emissions**
- ☁️ **Atmosphere** drives rainfall → affects **agriculture**
- 🌾 **Agriculture** produces methane → affects **atmosphere**
- 🏙️ **Cities** emit carbon → affect **ocean & forest**

Traditional single-model simulations fail to capture these **cross-domain interactions**. This project solves that using **independent autonomous agents** that communicate through an orchestrator.

---

## ✨ Features

### 🤖 Multi-Agent Simulation
- **5 independent AI agents** simulating different climate domains
- Each agent runs its own **physics-based simulation loop**
- Agents communicate and influence each other via the **Orchestrator**

### 🔬 Physics-Informed Models
- Thermodynamics (heat transfer between ocean ↔ atmosphere ↔ land)
- Carbon cycle (CO₂ flow across all domains)
- Radiation balance (solar input vs. Earth's emission)
- Fluid dynamics (ocean currents, atmospheric circulation)

### 🧠 Google Gemini AI Integration
- Real-time **climate predictions** with confidence scores
- **Auto-generated climate reports** in natural language
- **Interactive AI assistant** to query the simulation
- **What-if scenario reasoning** ("What if CO₂ doubles by 2050?")

### 📊 Digital Twin Dashboard
- Live climate metrics (temperature, CO₂, sea level, ice cover)
- Interactive **charts and visualizations** (Recharts)
- Real-time updates via **WebSockets**
- Historical timeline + future projections

### 🎮 Simulation Controls
- Play / Pause / Reset simulation
- Timeline slider (2024 → 2100)
- Scenario selector (baseline, high emission, green policy, extreme weather)
- Adjustable simulation speed

### 📁 Reports & Scenarios
- Generate & download AI-written climate reports
- Pre-loaded scenarios for quick demos
- Save and compare multiple scenarios

### 🎨 Beautiful UI
- Modern **dark-themed** interface with glassmorphism
- Smooth animations via **Framer Motion**
- Fully responsive (mobile + desktop)
- Interactive agent cards with live status

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                     FRONTEND (React + Vite)                 │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────┐  │
│  │  Dashboard   │  │  Agents Page │  │  Digital Twin    │  │
│  └──────────────┘  └──────────────┘  └──────────────────┘  │
│  ┌──────────────┐  ┌──────────────┐  ┌──────────────────┐  │
│  │ Predictions  │  │   Reports    │  │   AI Assistant   │  │
│  └──────────────┘  └──────────────┘  └──────────────────┘  │
└─────────────────────────────────────────────────────────────┘
                            │
                    REST API + WebSocket
                            │
┌─────────────────────────────────────────────────────────────┐
│                  BACKEND (Python + FastAPI)                 │
│                                                             │
│  ┌─────────────────────────────────────────────────────┐   │
│  │              ORCHESTRATOR (Coordinator)             │   │
│  └─────────────────────────────────────────────────────┘   │
│         │        │        │        │        │               │
│  ┌──────┴──┐ ┌───┴───┐ ┌──┴───┐ ┌──┴───┐ ┌──┴────┐         │
│  │ Ocean   │ │Forest │ │Atmos │ │Agri  │ │ City  │         │
│  │ Agent   │ │Agent  │ │Agent │ │Agent │ │Agent  │         │
│  └─────────┘ └───────┘ └──────┘ └──────┘ └───────┘         │
│                                                             │
│  ┌─────────────────┐  ┌─────────────────┐  ┌────────────┐ │
│  │ Physics Engine  │  │  Gemini Client  │  │ State Mgr  │ │
│  └─────────────────┘  └─────────────────┘  └────────────┘ │
└─────────────────────────────────────────────────────────────┘
                            │
                    ┌───────┴────────┐
                    │  SQLite DB     │
                    └────────────────┘
```

---

## 🧠 The 5 AI Agents

| Agent | Domain | Key Simulated Variables |
|-------|--------|-------------------------|
| 🌊 **Ocean Agent** | Marine systems | Sea surface temperature, pH, CO₂ absorption, sea level, salinity |
| 🌳 **Forest Agent** | Terrestrial ecosystems | Tree cover, CO₂ capture rate, biodiversity index, deforestation rate |
| ☁️ **Atmosphere Agent** | Weather & climate | Global temperature, greenhouse gas concentration, pressure, wind patterns |
| 🌾 **Agriculture Agent** | Food systems | Crop yield, soil health, water usage, methane emissions |
| 🏙️ **City Agent** | Urban environments | Population, energy consumption, carbon emissions, pollution index |

Each agent:
1. Runs an independent **physics-based simulation**
2. Sends its current state to the **Orchestrator**
3. Receives **cross-domain effects** from other agents
4. Uses **Gemini AI** for its own predictions and explanations

---

## 🛠️ Tech Stack

### Backend
| Technology | Purpose |
|------------|---------|
| **Python 3.10+** | Core backend language |
| **FastAPI** | REST API framework |
| **Uvicorn** | ASGI server |
| **SQLAlchemy** | ORM for SQLite |
| **SQLite** | Lightweight database |
| **Pydantic** | Data validation |
| **WebSockets** | Real-time communication |
| **Google Gemini API** | AI predictions & reports |
| **NumPy** | Physics calculations |
| **SciPy** | Scientific computing |

### Frontend
| Technology | Purpose |
|------------|---------|
| **React 18** | UI framework |
| **Vite** | Build tool |
| **TailwindCSS** | Styling |
| **Recharts** | Charts & graphs |
| **Framer Motion** | Animations |
| **React Router** | Routing |
| **Axios** | HTTP client |
| **Lucide React** | Icons |
| **React Three Fiber** | 3D Earth (optional) |

---

## 📁 Project Structure

```
climate-digital-twin/
├── backend/
│   ├── app/
│   │   ├── agents/          # 5 AI agents + orchestrator
│   │   ├── physics/         # Physics models
│   │   ├── ai/              # Gemini integration
│   │   ├── simulation/      # Simulation engine
│   │   ├── api/             # REST + WebSocket routes
│   │   ├── models/          # DB models
│   │   ├── schemas/         # Pydantic schemas
│   │   ├── services/        # Business logic
│   │   └── utils/           # Helpers
│   ├── data/                # Scenarios & seeds
│   ├── database/            # SQLite DB + migrations
│   └── tests/               # Unit tests
│
├── frontend/
│   └── src/
│       ├── components/      # Reusable components
│       ├── pages/           # Page components
│       ├── hooks/           # Custom React hooks
│       ├── services/        # API calls
│       ├── context/         # React context
│       └── utils/           # Helpers
│
└── docs/                    # Documentation
```

---

## ⚙️ Installation & Setup

### Prerequisites
- Python **3.10+**
- Node.js **18+** and npm
- Git
- Google Gemini API key ([get free key](https://aistudio.google.com/app/apikey))

### 🔧 Backend Setup

```bash
# 1. Clone the repository
git clone https://github.com/vishakha2121/climate-digital-twin.git
cd climate-digital-twin/backend

# 2. Create virtual environment
python -m venv venv
source venv/bin/activate        # Linux/Mac
venv\Scripts\activate           # Windows

# 3. Install dependencies
pip install -r requirements.txt

# 4. Create .env file
cp .env.example .env
# Edit .env and add your GEMINI_API_KEY

# 5. Initialize database
python scripts/init_db.py

# 6. Seed initial data
python scripts/seed_data.py

# 7. Run the backend
uvicorn main:app --reload --port 8000
```

Backend will run at: `http://localhost:8000`  
API docs: `http://localhost:8000/docs`

### 🎨 Frontend Setup

```bash
# 1. Navigate to frontend
cd ../frontend

# 2. Install dependencies
npm install

# 3. Create .env file
cp .env.example .env
# Make sure VITE_API_URL=http://localhost:8000

# 4. Run development server
npm run dev
```

Frontend will run at: `http://localhost:5173`

---

## 🔑 Environment Variables

### Backend (`.env`)
```env
GEMINI_API_KEY=your_gemini_api_key_here
DATABASE_URL=sqlite:///./database/climate_simulation.db
SECRET_KEY=your_secret_key_here
SIMULATION_INTERVAL=2
DEBUG=True
```

### Frontend (`.env`)
```env
VITE_API_URL=http://localhost:8000
VITE_WS_URL=ws://localhost:8000/ws
```

---

## 📡 API Endpoints

### Simulation
| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/simulation/start` | Start a new simulation |
| `POST` | `/api/simulation/stop` | Stop current simulation |
| `GET`  | `/api/simulation/status` | Get current simulation status |
| `GET`  | `/api/simulation/state` | Get full state of all agents |

### Agents
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET`  | `/api/agents` | List all 5 agents |
| `GET`  | `/api/agents/{id}` | Get specific agent details |
| `GET`  | `/api/agents/{id}/history` | Get agent's history |

### Predictions
| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/predictions/generate` | Generate AI prediction |
| `GET`  | `/api/predictions` | List all predictions |

### Reports
| Method | Endpoint | Description |
|--------|----------|-------------|
| `POST` | `/api/reports/generate` | Generate AI climate report |
| `GET`  | `/api/reports` | List all reports |
| `GET`  | `/api/reports/{id}` | Get specific report |

### Scenarios
| Method | Endpoint | Description |
|--------|----------|-------------|
| `GET`  | `/api/scenarios` | List available scenarios |
| `POST` | `/api/scenarios/load/{name}` | Load a scenario |

### WebSocket
| Endpoint | Description |
|----------|-------------|
| `ws://localhost:8000/ws` | Live simulation updates |

---

## 🎬 How It Works

1. **Simulation starts** → Orchestrator initializes all 5 agents with seed data
2. Each agent runs its **physics-based calculation** for one time step
3. Agents send their **current state** to the Orchestrator
4. Orchestrator **resolves cross-domain effects** (e.g., Forest absorbs City's CO₂)
5. Updated states are **broadcast via WebSocket** to the frontend
6. Frontend **renders live charts, metrics, and agent cards**
7. On demand, **Gemini AI** generates predictions & reports
8. User can **change scenarios** and re-run simulation

---

## 🧪 Running Tests

```bash
cd backend
pytest tests/ -v
```

---

## 🖼️ Screenshots

> Add screenshots here once the project is running

| Dashboard | Agents View |
|-----------|-------------|
| ![Dashboard](screenshots/dashboard.png) | ![Agents](screenshots/agents.png) |

| Simulation | Predictions |
|------------|-------------|
| ![Simulation](screenshots/simulation.png) | ![Predictions](screenshots/predictions.png) |

---

## 🚀 Future Scope

- 🌐 **3D Earth visualization** with React Three Fiber
- 🛰️ **Real satellite data** integration (NASA, NOAA APIs)
- 🧬 **Reinforcement learning** for climate policy optimization
- 🎯 **Fine-tuned climate foundation model**
- 👥 **Multi-user collaborative scenarios**
- 📱 **Mobile app** (React Native)

---

## 🎓 Learning Outcomes

This project demonstrates hands-on implementation of:

- ✅ **Physics AI** — embedding physical laws into AI simulations
- ✅ **Digital Twin** — real-time virtual replica of Earth's climate
- ✅ **Foundation Models** — using Gemini for reasoning and NLP
- ✅ **Multi-Agent Systems** — autonomous agents collaborating
- ✅ **Full-Stack Development** — Python backend + React frontend
- ✅ **Real-time Systems** — WebSocket-based live updates
- ✅ **API Design** — RESTful architecture with FastAPI

---

## 🤝 Contributing

This is a practice/learning project. Suggestions and improvements are welcome!

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## 📜 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## 👩‍💻 Author

**Vishakha**
- GitHub: [@vishakha2121](https://github.com/vishakha2121)
- Project Link: [climate-digital-twin](https://github.com/vishakha2121/climate-digital-twin)

---

## 🙏 Acknowledgements

- [Google Gemini AI](https://ai.google.dev) — for AI predictions & reasoning
- [FastAPI](https://fastapi.tiangolo.com) — for the blazing-fast backend
- [React](https://react.dev) — for the interactive UI
- [Recharts](https://recharts.org) — for beautiful charts
- [TailwindCSS](https://tailwindcss.com) — for styling
- [NASA Climate Data](https://climate.nasa.gov) — for physics references
- [IPCC Reports](https://www.ipcc.ch) — for climate science foundation

---

<div align="center">

### ⭐ If you found this project interesting, please give it a star! ⭐

**Made with 💙 for our planet 🌍**

</div>