# Quantum Fragility Simulator - Integrated Platform

An integrated educational platform featuring two quantum simulators: **Q-FRAG** (accurate physics-based) and **Quantum Circuit** (visual interactive). Learn quantum fragility through different approaches - from real quantum mechanics to intuitive visual metaphors.

##  Overview

This platform combines two complementary quantum simulators to provide a comprehensive learning experience:

1. **Q-FRAG (Quantum Fragility Simulator)**: Python-based backend with accurate quantum physics calculations
2. **Quantum Circuit Simulator**: Browser-based visual circuit builder with 3D visualization

Students can choose the simulator that best fits their learning style and level of expertise.

##  Key Features

### Platform Features
- **Dual Simulator Integration**: Seamlessly switch between two different simulators
- **Unified Interface**: Single entry point with clear simulator selection
- **Backend Status Monitoring**: Real-time health checks for Q-FRAG backend
- **Responsive Design**: Works on desktop, tablet, and mobile devices

### Q-FRAG Simulator Features
- ✅ Real quantum physics engine (Python/NumPy)
- ✅ Accurate T₁/T₂ decoherence modeling
- ✅ Multiple noise models (amplitude damping, phase damping, depolarizing)
- ✅ State vector visualization with Bloch sphere
- ✅ Time evolution tracking
- ✅ Export/import simulation configurations
- ✅ Measurement statistics and histograms

### Quantum Circuit Simulator Features
- ✅ Interactive 3D visualization (Three.js)
- ✅ Image-based quantum information
- ✅ Real-time metrics (coherence, entanglement, fidelity)
- ✅ Multiple quantum gates (H, CNOT, Phase, Identity, Measure)
- ✅ Visual degradation effects
- ✅ Educational tooltips and explanations
- ✅ Circuit builder with drag-and-drop

##  Quick Start

### Prerequisites

- **Node.js** 18+ (for Next.js app and Q-FRAG frontend)
- **Python** 3.8+ (for Q-FRAG backend)
- **npm** or **yarn**

### Installation

```bash
# Clone the repository
git clone <repository-url>
cd quantum-fragility-simulator

# Install Next.js dependencies
npm install

# Install Q-FRAG backend dependencies
cd amrits/backend
pip install -r requirements.txt
cd ../..

# Install Q-FRAG frontend dependencies
cd amrits/frontend
npm install
cd ../..
```

### Running the Full Platform

You need to start **three servers**:

#### 1. Main Next.js App (Port 3000)
```bash
npm run dev
```

#### 2. Q-FRAG Backend (Port 5000)
```bash
cd amrits/backend
python app.py
```

#### 3. Q-FRAG Frontend (Port 5173)
```bash
cd amrits/frontend
npm run dev
```

### Access Points

Once all servers are running:

- **Main Platform**: http://localhost:3000
- **Simulator Selection**: http://localhost:3000/simulator
- **Quantum Circuit Simulator**: http://localhost:3000/simulator/circuit
- **Q-FRAG Simulator (Integrated)**: http://localhost:3000/simulator/qfrag
- **Q-FRAG Direct Access**: http://localhost:5173

## 📖 Usage Guide

### Choosing a Simulator

Visit http://localhost:3000/simulator to see both options:

**Choose Q-FRAG if you want:**
- Accurate quantum physics calculations
- Real decoherence modeling (T₁, T₂ times)
- State vector analysis
- Research-grade simulations
- Graduate-level understanding

**Choose Quantum Circuit if you want:**
- Visual, intuitive learning
- 3D interactive experience
- Image-based quantum information
- Beginner-friendly interface
- Immediate visual feedback

### Using Q-FRAG Simulator

1. Navigate to http://localhost:3000/simulator/qfrag
2. Ensure backend status shows "Online" (green indicator)
3. Use the embedded interface or click "Open in New Tab"
4. Configure quantum state parameters
5. Select noise models and decoherence rates
6. Run simulation and observe state evolution
7. Export/import configurations as needed

### Using Quantum Circuit Simulator

1. Navigate to http://localhost:3000/simulator/circuit
2. Upload an image (PNG/JPEG, max 5MB)
3. Build a circuit by selecting gates and clicking qubits
4. Adjust environment parameters (noise, decoherence, gate errors)
5. Click "Start" to run the simulation
6. Watch 3D visualization and real-time metrics
7. Observe how quantum information degrades

## 🛠️ Technology Stack

### Main Platform (Next.js)
- **Framework**: Next.js 14+ with App Router
- **Language**: TypeScript
- **UI**: shadcn/ui + Tailwind CSS
- **State**: Zustand
- **3D**: Three.js + React Three Fiber

### Q-FRAG Backend
- **Language**: Python 3.8+
- **Framework**: Flask
- **Quantum**: NumPy, SciPy
- **API**: RESTful with CORS
- **Compression**: Flask-Compress

### Q-FRAG Frontend
- **Framework**: Vite + React
- **Language**: TypeScript
- **UI**: Material-UI / Custom components
- **Charts**: Recharts / D3.js
- **State**: React Context / Zustand

##  Project Structure

```
quantum-fragility-simulator/
├── app/                          # Next.js App Router
│   ├── page.tsx                 # Home page
│   ├── simulator/               # Simulator routes
│   │   ├── page.tsx            # Simulator selection
│   │   ├── circuit/            # Circuit simulator
│   │   └── qfrag/              # Q-FRAG integration
│   ├── learn/                   # Educational content
│   └── about/                   # About page
├── components/                   # React components
│   ├── circuit/                 # Circuit builder
│   ├── controls/                # Simulation controls
│   ├── education/               # Educational components
│   ├── metrics/                 # Metrics display
│   ├── visualization/           # Three.js 3D components
│   └── ui/                      # Base UI components
├── lib/                          # Core logic
│   ├── simulation/              # Simulation engine
│   ├── performance/             # Performance optimization
│   ├── animation/               # Animation system
│   └── errors/                  # Error handling
├── store/                        # State management
├── types/                        # TypeScript definitions
├── content/                      # Educational content
├── amrits/                       # Q-FRAG Simulator
│   ├── backend/                 # Python Flask API
│   │   ├── app.py              # Main Flask app
│   │   ├── api/                # API endpoints
│   │   ├── models/             # Quantum models
│   │   ├── noise/              # Noise models
│   │   └── tests/              # Backend tests
│   ├── frontend/                # React frontend
│   │   ├── src/                # Source code
│   │   ├── public/             # Static assets
│   │   └── package.json        # Frontend dependencies
│   └── docs/                    # Q-FRAG documentation
└── public/                       # Static assets
```

## 🎮 Development Commands

### Main Platform
```bash
npm run dev              # Start dev server
npm run build            # Build for production
npm run start            # Start production server
npm run lint             # Run ESLint
npm run test             # Run tests
```

### Q-FRAG Backend
```bash
cd amrits/backend
python app.py            # Start Flask server
python -m pytest         # Run tests
python -m pytest --cov   # Run with coverage
```

### Q-FRAG Frontend
```bash
cd amrits/frontend
npm run dev              # Start Vite dev server
npm run build            # Build for production
npm run preview          # Preview production build
npm run test             # Run tests
```

##  Architecture

### Integration Architecture

```
┌─────────────────────────────────────────┐
│     Main Next.js App (Port 3000)        │
│  ┌─────────────────────────────────┐   │
│  │   Simulator Selection Page      │   │
│  └─────────────────────────────────┘   │
│           │              │              │
│           ▼              ▼              │
│  ┌──────────────┐  ┌──────────────┐   │
│  │   Circuit    │  │    Q-FRAG    │   │
│  │  Simulator   │  │  Integration │   │
│  └──────────────┘  └──────────────┘   │
│                           │             │
└───────────────────────────┼─────────────┘
                            │
                            ▼
        ┌───────────────────────────────┐
        │  Q-FRAG Frontend (Port 5173)  │
        │  ┌─────────────────────────┐  │
        │  │   React UI Components   │  │
        │  └─────────────────────────┘  │
        └───────────────┬───────────────┘
                        │ HTTP/REST
                        ▼
        ┌───────────────────────────────┐
        │  Q-FRAG Backend (Port 5000)   │
        │  ┌─────────────────────────┐  │
        │  │   Flask API + Physics   │  │
        │  └─────────────────────────┘  │
        └───────────────────────────────┘
```

### Circuit Simulator Architecture

- **UI Layer**: React components with TypeScript
- **Visualization**: Three.js for 3D rendering
- **Simulation Engine**: Rule-based probabilistic quantum behavior
- **State Management**: Zustand for reactive state
- **Performance**: Object pooling, computation caching, lazy loading

### Q-FRAG Architecture

- **Backend**: Flask REST API with quantum physics calculations
- **Frontend**: React SPA with state visualization
- **Communication**: RESTful API with JSON payloads
- **Physics**: NumPy/SciPy for accurate quantum mechanics

## 🎓 Educational Approach

### Dual Learning Paths

**Path 1: Visual Intuition (Circuit Simulator)**
- Start with visual metaphors
- Learn through observation
- Build intuition first
- Minimal mathematics
- Immediate feedback

**Path 2: Physics Accuracy (Q-FRAG)**
- Start with real physics
- Learn through calculation
- Understand formulas
- Graduate-level content
- Accurate simulations

### Recommended Learning Sequence

1. **Beginners**: Start with Circuit Simulator
   - Upload images and see visual degradation
   - Build simple circuits (H, CNOT)
   - Observe metrics changing
   - Read educational tooltips

2. **Intermediate**: Explore both simulators
   - Compare visual vs. physics-based approaches
   - Understand T₁/T₂ times in Q-FRAG
   - Build complex circuits
   - Experiment with noise models

3. **Advanced**: Focus on Q-FRAG
   - Analyze state vectors
   - Study decoherence models
   - Export/import configurations
   - Research-grade simulations

## 🔧 Configuration

### Environment Variables

Create `.env.local` in the root directory:

```env
# Main App
NEXT_PUBLIC_API_URL=http://localhost:3000/api

# Q-FRAG Integration
NEXT_PUBLIC_QFRAG_BACKEND_URL=http://localhost:5000
NEXT_PUBLIC_QFRAG_FRONTEND_URL=http://localhost:5173
```

### Q-FRAG Backend Configuration

Edit `amrits/backend/config.py` (if exists) or use environment variables:

```python
# Flask configuration
DEBUG = True
HOST = "0.0.0.0"
PORT = 5000

# CORS settings
CORS_ORIGINS = ["http://localhost:3000", "http://localhost:5173"]

# Simulation limits
MAX_QUBITS = 10
MAX_TIME_STEPS = 1000
```

##  Testing

### Main Platform Tests
```bash
npm run test              # All tests
npm run test:unit         # Unit tests
npm run test:integration  # Integration tests
npm run test:properties   # Property-based tests
npm run test:coverage     # Coverage report
```

### Q-FRAG Backend Tests
```bash
cd amrits/backend
python -m pytest                    # All tests
python -m pytest tests/test_*.py    # Specific test file
python -m pytest --cov              # With coverage
python -m pytest -v                 # Verbose output
```

### Q-FRAG Frontend Tests
```bash
cd amrits/frontend
npm run test              # Run tests
npm run test:watch        # Watch mode
npm run test:coverage     # Coverage report
```

##  Deployment

### Production Build

```bash
# Build main platform
npm run build
npm run start

# Build Q-FRAG frontend
cd amrits/frontend
npm run build

# Deploy Q-FRAG backend
cd amrits/backend
# Use gunicorn or uwsgi for production
gunicorn -w 4 -b 0.0.0.0:5000 app:app
```


##  Troubleshooting

### Q-FRAG Backend Not Starting

**Issue**: Backend shows "Offline" status

**Solutions**:
1. Check if Python is installed: `python --version`
2. Install dependencies: `pip install -r amrits/backend/requirements.txt`
3. Check port 5000 is not in use: `netstat -ano | findstr :5000`
4. Start backend manually: `cd amrits/backend && python app.py`
5. Check backend logs for errors

### Q-FRAG Frontend Not Loading

**Issue**: Frontend shows blank page or errors

**Solutions**:
1. Check if Node.js is installed: `node --version`
2. Install dependencies: `cd amrits/frontend && npm install`
3. Check port 5173 is not in use
4. Clear browser cache (Ctrl+Shift+R)
5. Check console for errors (F12)

### Circuit Simulator Issues

**WebGL not supported**:
- Update graphics drivers
- Use modern browser (Chrome, Firefox, Edge)
- Enable hardware acceleration

**Image upload fails**:
- Check file format (PNG/JPEG only)
- Ensure file size < 5MB
- Try different image

**Simulation not starting**:
- Upload image first
- Add at least one gate
- Check browser console (F12)

### CORS Errors

**Issue**: Cross-origin request blocked

**Solutions**:
1. Ensure Q-FRAG backend has CORS enabled (it should by default)
2. Check `amrits/backend/app.py` has `CORS(app)`
3. Verify URLs in `.env.local` are correct
4. Restart all servers

## 📊 Comparison: Q-FRAG vs Circuit Simulator

| Feature | Q-FRAG | Circuit Simulator |
|---------|--------|-------------------|
| **Physics Accuracy** | ⭐⭐⭐⭐⭐ Real quantum mechanics | ⭐⭐⭐ Rule-based approximation |
| **Visual Appeal** | ⭐⭐⭐ Charts and graphs | ⭐⭐⭐⭐⭐ 3D interactive visualization |
| **Ease of Use** | ⭐⭐⭐⭐ Moderate learning curve | ⭐⭐⭐⭐⭐ Very intuitive |
| **Target Audience** | Graduate students, researchers | Undergraduates, beginners |
| **Backend** | Python/Flask (required) | Browser-based (no backend) |
| **Decoherence** | Accurate T₁/T₂ modeling | Simplified exponential decay |
| **State Visualization** | Bloch sphere, state vector | 3D qubit spheres, connections |
| **Noise Models** | Multiple (amplitude, phase, depolarizing) | Single combined model |
| **Export/Import** | ✅ Yes | ❌ No |
| **Performance** | Limited by Python | Optimized with caching |

##  Contributing

Contributions welcome! Please:
- Maintain educational focus
- Add tests for new features
- Update documentation
- Follow existing code style
- Test both simulators

##  License

Educational use only.

##  Acknowledgments

- **Circuit Simulator**: Built with spec-driven development methodology
- **Q-FRAG**: Advanced quantum physics simulation engine
- **Integration**: Unified platform for comprehensive quantum education



## 📚 Additional Resources

- **Circuit Simulator Docs**: See main README sections above
- **Q-FRAG Docs**: See `amrits/docs/` directory
- **API Documentation**: See `amrits/backend/docs/`
- **User Guide**: Visit http://localhost:3000/learn

---

**Important Notes**:
- Circuit Simulator is for **visual intuition** and **educational purposes**
- Q-FRAG is for **accurate physics** but still **educational**, not production-grade
- Neither simulator should be used for real quantum computing research
- Both are designed to help students understand quantum fragility concepts

**Version**: 2.0.0 (Integrated Platform)  
**Last Updated**: February 2026
