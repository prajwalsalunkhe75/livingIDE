
# 🧬 Living IDE

A bio-adaptive development environment that reads your cognitive state (HRV, keystrokes, facial expressions) and adapts VS Code in real-time.

The current MVP features a fully functional Python backend that ingests keystroke dynamics, fuses them with simulated HRV, runs a cognitive state machine, and broadcasts the result via WebSocket.

### Structure (MVC)
- **Models**: Data classes for signals (`KeystrokeMetrics`, `HRVMetrics`) and the core `CognitiveState`.
- **Services**: Pynput listener, simulated HRV, and state fusion algorithm.
- **Controllers**: Orchestrates signals, runs the FSM hysteresis, and manages SQLite session logging.
- **Views**: Pushes real-time updates to Console (Rich terminal) and WebSocket clients.
- **Demo Dashboard**: A glassmorphism HTML dashboard visualizing the telemetry.

### Running the Engine
1. Install dependencies: `pip install -r backend/requirements.txt`
2. Start the backend: `python backend/main.py`
3. Open `demo/index.html` in your browser.
4. Type anywhere on your computer — watch the dashboard react to your keystroke dynamics in real-time.
