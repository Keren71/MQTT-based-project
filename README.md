MQTT Weather Station
A real-time weather monitoring app that collects temperature & humidity data via MQTT, stores it in SQLite, and visualizes live updates with 5-minute averages.

Features
🌡️ Real-time temperature & humidity tracking
📊 Interactive charts with 5-minute averages
💾 Data storage for historical trends
📱 Fully responsive design
Setup
Prerequisites
Node.js (v14+)
npm (v6+)
Installation
bash
Copy
Edit
git clone https://github.com/Keren71/MQTT-based-project
cd MQTT-based-project
npm install
mkdir -p public && cp index.html public/
npm start
Access at http://localhost:3000

Project Structure
bash
Copy
Edit
MQTT-based-project/
├── public/         # Frontend (Chart.js visualization)
├── server.js       # Express API logic
├── package.json    # Dependencies
└── README.md       # Documentation
How It Works
Live Data Feed → The frontend connects to MQTT & displays real-time temperature and humidity.
Storage & Processing → Data is stored and averaged every 5 minutes.
Visualization → Interactive charts update automatically.
API Endpoints
POST /api/weather/data → Store readings
GET /api/weather/history → Retrieve 5-minute averages
