# Autonomous Drone Navigation with Multi-Agent AI Orchestrator  
*A fully simulation-based autonomous drone navigation system using coordinated AI agents — no hardware required.*

-This project builds a fully autonomous drone navigation system using a multi-agent AI architecture, operating entirely inside a simulation. The agents learn to move from start to goal while avoiding obstacles using imitation learning, evaluation pipelines, and automated reporting. Everything runs in Google Colab or Jupyter Notebook, making it accessible even without drone hardware.

---

## Problem Statement  
Traditional drone navigation experiments require:
- Expensive sensors  
- Real drones  
- Risky field testing  
- Slow prototype cycles  

To make autonomous drone research accessible, this project implements a complete navigation pipeline in simulation, where a drone:
- Learns from expert A* paths  
- Avoids obstacles  
- Navigates efficiently  
- Gets evaluated automatically  

This results in safer, faster, cheaper drone AI development.

---

## 🤖 Why Multi-Agent AI?  
A multi-agent architecture makes the system modular, scalable, and automated.

| Agent | Role |
|-------|------|
| **DataAgent** | Creates environments + expert paths |
| **ModelAgent** | Trains the navigation model (MLP) |
| **EvalAgent** | Tests policy on unseen maps |
| **ReportAgent** | Generates report + GIF |
| **OrchestratorAgent** | Controls entire workflow automatically |

This mirrors real autonomous systems where perception, planning, learning, evaluation, and reporting are separated.

---

## 🏗 Architecture  
The workflow: DataAgent → ModelAgent → EvalAgent → ReportAgent → OrchestratorAgent.


### 🔹 DataAgent  
- Generates random obstacle maps  
- Computes optimal expert paths using A*  
- Creates training datasets  

### 🔹 ModelAgent  
- Trains an MLP neural-network policy using imitation learning  
- Learns to mimic the expert A* planner  

### 🔹 EvalAgent  
- Runs 40 simulated evaluation episodes  
- Tracks:
  - Success rate  
  - Collision rate  
  - Average episode length  

### 🔹 ReportAgent  
Outputs:
- `outputs/report.txt` (performance metrics)  
- `outputs/demo.gif` (navigation animation)

### 🔹 OrchestratorAgent  
- Automates the entire pipeline  
- Handles data → training → evaluation → reporting

---

## 🎥 Demo Output  

### 📄 `outputs/report.txt`  
Contains:
- Success rate  
- Collision rate  
- Average path length  
- Summary of evaluation results  

### 🎞 `outputs/demo.gif`  
An animated visualization of the drone navigating through obstacles toward the goal.

---

## 🔧 Technologies Used  
- Python 3  
- Google Colab / Jupyter Notebook  
- NumPy  
- Matplotlib  
- scikit-learn  
- Pillow  
- A* pathfinding  
- Modular AI agent architecture  

Everything runs entirely in simulation, no drone hardware required.

---

## 📂 Project Structure  

autonomous-drone-ai-agent/
│
├── autonomous-drone-with-ai-navigation-orchestrator.ipynb
│
├── outputs/
│ ├── report.txt
│ └── demo.gif
│
└── README.md


---

## ▶️ How to Run  

### 1. Google Colab

1. Upload the project folder to Google Drive  
2. Open Colab → New Notebook  
3. Mount Drive:

from google.colab import drive
drive.mount('/content/drive')

drive.mount('/content/drive')
Navigate to project directory:



