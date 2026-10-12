# Turbo Smash Karts 3D 🏎️💥

A production-ready 3D multiplayer kart battle arena game inspired by [Smash Karts](https://www.smashkarts.io/), built with **Three.js**, **Web Audio API**, and **WebSocket**.

---

## 🚀 Quick Start

### 1. Standalone Singleplayer & Local Mode
Open `index.html` directly in any modern web browser. You can immediately jump into battle with intelligent AI bots.

### 2. Real-Time Online / Local Multiplayer
To host rooms and play with multiple real players:

```bash
# 1. Install dependencies
npm install

# 2. Start the WebSocket and HTTP server
npm start
```

Visit **`http://localhost:3000`** in multiple browser tabs or invite friends on your local network.

---

## 🎮 Game Features

### 💥 Signature Smash Karts Combat
- **Mystery Boxes (`?` Box)**: Floating rotating question mark boxes scattered around the arena that drop randomized power-ups with live respawn countdowns.
- **Weapon Arsenal**:
  - 🚀 **Homing Rocket**: Target-tracking missile with smoke exhaust and fireball blast.
  - 🔫 **Gatling Gun**: Rapid-fire kinetic bullet burst.
  - 💣 **Spike Mine**: Deployable proximity trap with a flashing LED beacon.
  - ⭐ **Invincible Nitro**: Blazing speed boost and invulnerability shield that instantly smashes opponents upon ramming.
  - 🏐 **Cannon Bomb**: Bouncing explosive cannonball that ricochets off arena walls.
- **Health & Smash System**: 100 HP per kart, overhead damage flashes, live killfeed, and respawn protection shields.

### 🌐 Production Multiplayer
- **Multi-Room Lobby**: Host creates a unique 5-letter Room Code (e.g. `TURBO`); guests join using the code.
- **Authoritative Sync**: 20Hz state tick synchronizing positions, headings, weapon firing, health, and match timer.
- **Client Interpolation**: Smooth linear position lerping and slerp rotation for remote karts to eliminate rubberbanding.
- **Offline / Local AI Fallback**: If offline or playing solo, intelligent AI bots automatically populate the arena.

### 🚗 Customization Garage
- **4 Kart Chassis**: Standard Racer, Speedster F1, Buggy Beast, and Cyber Cruiser.
- **8 Driver Hats**: Crown 👑, Horns 😈, Cap 🧢, Propeller 🚁, Police 👮, Chef 👨‍🍳, Mohawk 🎸, and Angel Halo 😇.
- **4 Wheel Styles**: Classic Slicks, Offroad Spikes, Cyber Neon, and Gold Alloys.
- **4 Exhaust Trails**: Nitro Fire, Cyan Plasma, Rainbow Stars, and Smoke.
- **Vibrant Paint Finish**: 8 color swatches + custom nickname tag.

### ⚙️ Full Settings Suite
- **Graphics Quality Presets**: Low, Medium, High, Ultra.
- **Dynamic Shadows & Resolution Scaling**: 0.8x, 1.0x, 1.5x.
- **Camera Views**: Chase (Close), Chase (Far), Cockpit / First Person, and Top-Down Drone.
- **Field of View (FOV)**: 60° to 95° slider.
- **Audio Mixer**: Separate Master Volume and Engine Rumble sliders.
- **Keybinding Remapper**: Remap Accelerate, Brake, Steer, Fire, and Drift to any key.
- **Mobile Touch Controls**: On-screen virtual buttons for mobile and touch devices.
- **Settings Persistence**: All customization choices, settings, and player stats are saved to `localStorage`.

---

## ☁️ Deployment Guide: Render vs Vercel vs Netlify

| Platform | Suitable for Multiplayer? | Why? |
| :--- | :---: | :--- |
| **Render** | **YES (Recommended)** | Runs persistent Node.js Web Services with continuous WebSocket (`ws://`/`wss://`) support, 20Hz ticks, and in-memory rooms. Free tier available. |
| **Vercel** | Frontend Only | Serverless platform; terminates requests after 10-15s and does not support persistent stateful WebSockets for real-time gaming. |
| **Netlify** | Frontend Only | Serverless platform; does not support long-lived persistent WebSocket connections. |

### Deploy to Render (Recommended - Free)

1. Push your repository to GitHub: `https://github.com/Sushanth-Patel/Smash-Karts-V2`.
2. Go to [Render.com](https://render.com) and click **New +** -> **Web Service**.
3. Select your repository `Smash-Karts-V2`.
4. Render will auto-detect the configuration from `render.yaml`:
   - **Environment**: `Node`
   - **Build Command**: `npm install`
   - **Start Command**: `npm start`
5. Click **Create Web Service**.
6. Once deployed, Render provides a free live HTTPS URL (e.g. `https://smash-karts-v2.onrender.com`).
   - The game and WebSocket server will run automatically at that URL!
   - Share the URL with friends to play anywhere!

