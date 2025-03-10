MQTT Weather Station
This app collects temperature & humidity data via MQTT, stores it in SQLite, and visualizes it with real-time updates and 5-minute averages.

Features
🌡️ Live temperature & humidity monitoring
📊 Interactive charts with 5-minute averages
💾 SQLite storage for historical data
📱 Responsive design
Setup
Prerequisites
Node.js (v14+)
npm (v6+)


Installation
bash
Copy
Edit
git clone https://github.com/yourusername/mqtt-weather-app
cd mqtt-weather-app
npm install
mkdir -p public && cp index.html public/
npm start
Access at http://localhost:3000


Project Structure
bash
Copy
Edit
mqtt-weather-app/
├── public/         # Frontend (Chart.js visualization)
├── server.js       # Express API & SQLite logic
├── package.json    # Dependencies
├── weather_data.db # SQLite database
└── README.md       # Documentation
How It Works
Frontend connects to MQTT & displays live data
Backend stores MQTT messages in SQLite
Every 5 minutes, averages are calculated & saved
Chart updates with 1-hour historical data
API Endpoints
POST /api/weather/data → Store readings
GET /api/weather/history → Retrieve 5-minute averages
Database Schema
Raw Data Table
sql
Copy
Edit
CREATE TABLE raw_data (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  type TEXT NOT NULL,  -- 'temperature' or 'humidity'
  value REAL NOT NULL, -- Sensor reading
  timestamp TEXT NOT NULL -- ISO format
);
5-Minute Averages Table
sql
Copy
Edit
CREATE TABLE avg_data (
  id INTEGER PRIMARY KEY AUTOINCREMENT,
  avg_temperature REAL,
  avg_humidity REAL,
  timestamp TEXT NOT NULL
);