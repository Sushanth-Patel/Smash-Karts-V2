# Turbo Smash Karts 3D

Real-time 3D kart combat for the browser, built with Three.js, Node.js, and WebSocket. Race, collect power-ups, and battle other players in a fast arena game with offline AI support.

[![Repository](https://img.shields.io/badge/GitHub-Repository-181717?style=for-the-badge&logo=github)](https://github.com/Sushanth-Patel/Turbo-Kart)

## Overview

Turbo Smash Karts 3D supports both solo play and real-time multiplayer. The browser runs the Three.js game client while the Node.js server hosts rooms and synchronizes multiplayer state over WebSocket.

## Features

### Combat

- Collect rotating mystery boxes and randomized power-ups.
- Use homing rockets, gatling guns, spike mines, cannon bombs, and nitro.
- Track health, damage, eliminations, respawns, and temporary protection shields.

### Multiplayer

- Create or join a room with a short room code.
- Synchronize kart movement, rotation, weapons, health, and match timers.
- Interpolate remote players for smoother movement.
- Fall back to AI bots when playing solo or offline.

### Customization

- Choose from four kart chassis.
- Equip driver hats, wheel styles, and exhaust trails.
- Select a paint color and player nickname.

### Settings and controls

- Low, Medium, High, and Ultra graphics presets.
- Dynamic shadows and resolution scaling.
- Chase, cockpit, and top-down camera views.
- Adjustable field of view and audio mixer controls.
- Remappable keyboard bindings.
- Touch controls for mobile devices.
- Persistent settings and player stats stored in `localStorage`.

## Requirements

- Node.js 18 or newer
- npm
- A modern browser with WebGL and WebSocket support

## Run locally

Clone the repository and install dependencies:

```bash
git clone https://github.com/Sushanth-Patel/Turbo-Kart.git
cd Turbo-Kart
npm install
```

Start the game server:

```bash
npm start
```

Open [http://localhost:3000](http://localhost:3000) in a browser. Open the URL in additional tabs or on other devices connected to the same network to test multiplayer.

The game can also be opened directly from `index.html` for solo play, but running the server is required for room-based multiplayer.

## Deployment

### Render

Render is the recommended deployment target because the game server needs a long-running Node.js process for WebSocket connections.

1. Create a new Web Service on [Render](https://render.com).
2. Connect the `Sushanth-Patel/Turbo-Kart` repository.
3. Use the included `render.yaml`, or set:
   - **Build command:** `npm install`
   - **Start command:** `npm start`
   - **Environment:** `Node`
4. Deploy and open the HTTPS URL provided by Render.

### Frontend-only hosting

Static hosts such as Netlify and Vercel can serve the browser client, but they do not host the persistent WebSocket server required for real-time multiplayer. Use them only when the client is configured to connect to a separately deployed Node.js server.

## Project structure

```text
.
├── index.html       # Three.js game client and interface
├── server.js        # HTTP server and WebSocket multiplayer server
├── package.json     # Scripts and dependencies
├── render.yaml      # Render deployment configuration
├── netlify.toml     # Static hosting configuration
└── vercel.json      # Vercel configuration
```

## Available scripts

| Command | Description |
| --- | --- |
| `npm start` | Start the HTTP and WebSocket server |
| `npm run server` | Alias for `npm start` |
| `npm run dev` | Start the development server |

## Live demo

Play the deployed game at [turbo-kart-7e0n.onrender.com](https://turbo-kart-7e0n.onrender.com/).

## License

The project is released under the MIT License, as declared in `package.json`.
