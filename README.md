# 🛰️ Airport Infrastructure Editor PRO
> **Industrial CAD Design System for Aviation Mapping & Infrastructure Planning.**

![Build Status](https://img.shields.io/badge/build-passing-brightgreen)
![Version](https://img.shields.io/badge/version-5.3.0--PRO-orange)
![Platform](https://img.shields.io/badge/platform-windows-blue)
![Security](https://img.shields.io/badge/security-V8--Bytecode-red)

Airport Infrastructure Editor PRO is a specialized CAD tool designed for the precise creation and management of airport networks. From taxiway routing to complex gate zoning, this editor provides engineers and simulation developers with a high-performance environment focused on accuracy and data security.

---

## ⚡ Key Features

* **Industrial Ribbon UI** – Intuitive control scheme inspired by professional engineering software for maximum workflow efficiency.
* **V8 Bytecode Engine** – The application core (`manager_renderer.jsc`) is protected via binary compilation, preventing source code exposure.
* **Smart Snapping** – Intelligent node-to-track snapping ensures perfectly smooth path connections and alignment.
* **Complex Zoning** – Color-coded polygons for Runways, Taxiways, and Gate stands with custom metadata support.
* **Seed-Based Licensing** – Integrated offline license verification system using the `XXXX-XXXX-XXXX-XXXX` format.
* **Recent Projects Dashboard** – Home screen with project history, statistics, and automated state recovery.

---

## 🛠️ Requirements

Before starting development or building the application, ensure you have the following installed:

* **Node.js** (v18.x or newer)
* **npm** (Included with Node.js)
* **Electron** (v30.x)
* **Bytenode** (Required for binary compilation)
* **Git** (For version control)

---

## 📦 Installation

### 1. Clone the Repository
```bash
git clone [https://github.com/your-username/airport-editor.git](https://github.com/your-username/airport-editor.git)
cd airport-editor
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Prepare the Binary Core (Critical)
The application logic runs on secured bytecode. You must compile the renderer before the first run:
```bash
npx electron ./node_modules/bytenode/lib/cli.js --compile manager_renderer.js
```

### 4. Run the Application
```bash
npm start
```

---

## 🎮 Usage

### Control Schemes (Hotkeys)
The editor uses standard CAD shortcuts for rapid object manipulation:

| Key | Mode | Description |
| :--- | :--- | :--- |
| **F1** | `PAN_MODE` | Free map movement and object selection. |
| **F2** | `NODE_MODE` | Place nodes (utilizes smart auto-snapping). |
| **F3** | `TRACK_MODE` | Create linear and curved taxiway paths (Bezier). |
| **F4** | `ZONE_MODE` | Draw polygons (Double-click to close the zone). |
| **DEL** | `DELETE` | Remove the selected element or group. |
| **CTRL+G** | `GROUP` | Group selected tracks into a single logical entity. |
| **CTRL+Z** | `UNDO` | Step back in the action history. |

### Export Process
1. Click the **SAVE .APRT** icon in the top ribbon menu.
2. Fill in the project metadata (ICAO code, Airport Name, Author).
3. If the PRO version is activated, the 50-node limit is removed, and the project is exported as a structured JSON/APRT file.

---

## 🚀 Building the Distribution (.EXE)

To generate a production-ready Windows installer:

```powershell
# Compiles the bytecode and generates an NSIS installer in the /dist folder
npm run build
```

---

## 🛡️ License & Security
This software is distributed under a **Proprietary License**. The core logic is protected using **Bytenode** technology. 

**Warning:** Never include the plain `manager_renderer.js` in a production build. Always ensure `manager_renderer.jsc` is present and correctly linked via `loader.js`.

---

**Author:** [Hobza]  
**Contact:** [your-email@domain.com]  
*Airport Infrastructure Editor - Professional Tools for Modern Aviation.*
