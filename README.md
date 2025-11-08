# Doctor-Patient Chat System over Sockets

A minimal real-time chat between a doctor and a patient using Node.js, Express, and Socket.IO.

## Features
- Join as Doctor or Patient
- Connect via shared Patient ID (room-based)
- Real-time messaging
- Typing indicator
- Presence list for the room

## Requirements
- Node.js 18+ installed (`node -v`)

## Setup

```bash
# In PowerShell from the project directory
npm install
npm run start
```

Then open `http://localhost:3000` in two different browser windows or devices:
- Join one as Patient with a Patient ID (e.g., P1234)
- Join the other as Doctor using the same Patient ID

You can also open multiple tabs to simulate both roles locally.

## How it works
- The backend serves static files from `public/` and hosts a Socket.IO server.
- Both Doctor and Patient join the same room named `chat:<PatientID>`.
- Messages are broadcast only within that room.
- Presence and typing events are pushed to clients in real time.

## File Structure
```
server.js              # Express + Socket.IO server
public/index.html      # UI (role selection, patient ID, chat)
public/script.js       # Client-side Socket.IO logic
public/styles.css      # Basic styling
package.json           # Dependencies and scripts
```

## Customization
- Add authentication, database storage, or multi-patient dashboards as needed.
- Replace in-memory presence with a database or Redis for scale.

## Scripts
- `npm start` — start server on port 3000
- `npm run dev` — start with nodemon (auto-reload)

## Notes
This example is intentionally simple and does not include user authentication or message persistence.

## Docker

Requirements:
- Docker Desktop (Windows) or Docker Engine

Build and run with Docker:

```bash
# In project root
docker compose up --build -d

# Open the app
start http://localhost:3000

# To view logs
docker compose logs -f

# To stop
docker compose down
```











