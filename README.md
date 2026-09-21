# Adaptive Emergency Evacuation Route Optimization

An emergency evacuation route optimization system built using **C++,
Data Structures & Algorithms (DSA), and Object-Oriented Programming (OOP)**.

The system models a road network as a **weighted graph** and uses
**Dijkstra's Algorithm with a Priority Queue / Min-Heap** to calculate
suitable evacuation routes. When road conditions change due to a
simulated emergency such as flooding, road blockage, or increased risk,
the corresponding road weight is updated and an alternate route is
calculated.

---

## 📌 Project Overview

During emergencies such as floods, fires, or blocked roads, a previously
suitable route may become unsafe or unavailable.

This project represents the road network as a **weighted graph**:

- Locations are represented as graph nodes.
- Roads are represented as weighted edges.
- Road weights represent the current cost of travelling through a road.
- Emergency conditions modify the status or weight of affected roads.
- Dijkstra's Algorithm calculates a new suitable route after the network
  changes.

The project focuses on applying **Data Structures, Algorithms, and
Object-Oriented Programming concepts in C++** to a practical emergency
evacuation problem.

The initial system uses **predefined road-network data and simulated
emergency scenarios** for testing.

---

## 🏗️ System Architecture

```text
                         USER
                           │
                           ▼
                 ┌───────────────────┐
                 │   React Frontend  │
                 │   Web Interface   │
                 └─────────┬─────────┘
                           │
                       HTTP / JSON
                           │
                           ▼
                 ┌───────────────────┐
                 │    C++ API Layer  │
                 │  HTTP / Services  │
                 └─────────┬─────────┘
                           │
                           ▼
                 ┌───────────────────┐
                 │ Disaster Manager  │
                 │ Road Conditions   │
                 └─────────┬─────────┘
                           │
                           ▼
                 ┌───────────────────┐
                 │       Graph       │
                 │  Adjacency List   │
                 └─────────┬─────────┘
                           │
                           ▼
                 ┌───────────────────┐
                 │  Route Optimizer  │
                 └─────────┬─────────┘
                           │
                           ▼
              ┌─────────────────────────┐
              │ Dijkstra's Algorithm    │
              │ + Priority Queue/MinHeap│
              └───────────┬─────────────┘
                          │
                          ▼
                 ┌───────────────────┐
                 │ Path Reconstruction│
                 └─────────┬─────────┘
                           │
                           ▼
                    EVACUATION ROUTE
[1] USER INPUT
      │
      ├── Origin / Starting Location
      └── Destination / Evacuation Center
      │
      ▼

[2] ROAD NETWORK DATA
      │
      ├── Locations → Graph Nodes
      └── Roads → Weighted Graph Edges
      │
      ▼

[3] ROUTE CALCULATION
      │
      ├── Dijkstra's Algorithm
      └── Priority Queue / Min-Heap
      │
      ▼

[4] INITIAL ROUTE
      │
      └── Suitable evacuation route generated
      │
      ▼

[5] EMERGENCY CONDITION UPDATE
      │
      ├── Road blocked
      ├── Road becomes risky
      └── Road weight is changed
      │
      ▼

[6] ROUTE RE-CALCULATION
      │
      ├── Updated graph is processed
      └── Dijkstra calculates an alternate route
      │
      ▼

[7] UPDATED EVACUATION ROUTE
      │
      └── Route bypasses affected road(s)
#PROJECT STRUCTURE:-
Adaptive-Emergency-Evacuation/
│
├── backend/
│   ├── include/
│   │   ├── Location.h
│   │   ├── Road.h
│   │   ├── Graph.h
│   │   ├── RouteOptimizer.h
│   │   ├── DisasterManager.h
│   │   └── APIClient.h
│   │
│   ├── src/
│   │   ├── main.cpp
│   │   ├── Location.cpp
│   │   ├── Road.cpp
│   │   ├── Graph.cpp
│   │   ├── RouteOptimizer.cpp
│   │   ├── DisasterManager.cpp
│   │   └── APIClient.cpp
│   │
│   ├── algorithms/
│   │   ├── Dijkstra.cpp
│   │   ├── PriorityQueue.cpp
│   │   └── PathReconstruction.cpp
│   │
│   └── data/
│       ├── roads.json
│       ├── locations.json
│       └── emergency_scenarios.json
│
├── frontend/
│   ├── public/
│   │   └── assets/
│   │
│   ├── src/
│   │   ├── components/
│   │   │   ├── Navbar.tsx
│   │   │   ├── LocationSelector.tsx
│   │   │   ├── RouteCard.tsx
│   │   │   ├── RoadStatusCard.tsx
│   │   │   ├── EmergencyPanel.tsx
│   │   │   ├── RouteDetails.tsx
│   │   │   └── MapView.tsx
│   │   │
│   │   ├── pages/
│   │   │   ├── Home.tsx
│   │   │   ├── RoutePlanner.tsx
│   │   │   ├── EmergencyMode.tsx
│   │   │   └── Results.tsx
│   │   │
│   │   ├── services/
│   │   │   └── api.ts
│   │   │
│   │   ├── types/
│   │   │   └── route.ts
│   │   │
│   │   ├── App.tsx
│   │   ├── main.tsx
│   │   └── index.css
│   │
│   ├── package.json
│   └── vite.config.ts
│
├── tests/
│   ├── test_graph.cpp
│   ├── test_dijkstra.cpp
│   ├── test_route_optimizer.cpp
│   └── test_disaster_manager.cpp
│
├── docs/
│   ├── architecture.md
│   └── api.md
│
├── CMakeLists.txt
└── README.md



🔌 API & Integration Layer
The project includes an API layer connecting the React frontend with
the C++ backend.
React Frontend
      │
      │ HTTP / JSON
      ▼
C++ API Layer
      │
      ▼
Route / Emergency Services
      │
      ▼
C++ DSA Core
The backend uses libcurl for HTTP communication where required by
the API integration.
The API layer is kept separate from the core graph and algorithm
implementation so that the DSA logic remains modular and testable.
🧪 Testing
The project includes separate tests for the major components:
tests/
├── test_graph.cpp
├── test_dijkstra.cpp
├── test_route_optimizer.cpp
└── test_disaster_manager.cpp
Testing includes:
- Graph creation
- Road connectivity
- Shortest-path calculation
- Priority queue operations
- Path reconstruction
- Blocked-road scenarios
- Risky-road scenarios
- Alternate route calculation
🛠️ Technology Stack
Backend
- C++
- C++ OOP
- Data Structures & Algorithms
- CMake
- libcurl
Algorithms
- Graph
- Adjacency List
- Dijkstra's Algorithm
- Priority Queue / Min-Heap
- Path Reconstruction
Frontend
- React
- TypeScript
- Vite
- CSS
- HTTP / JSON API Integration
Data
- JSON
- Predefined road-network data
- Predefined emergency scenarios
🎯 Project Objectives
The project aims to demonstrate how DSA and OOP concepts can be applied
to a practical emergency evacuation problem.
The main objectives are:
1. Model a road network using a weighted graph.
2. Implement Dijkstra's Algorithm for route optimization.
3. Implement a Priority Queue / Min-Heap for efficient node selection.
4. Dynamically update road conditions.
5. Recalculate routes when emergency conditions change.
6. Apply OOP principles through modular C++ classes.
7. Provide a web-based interface for interacting with the system.
8. Test the system under different simulated emergency conditions.
📈 Expected Outcome
The final prototype will:
- Accept a starting location and destination.
- Represent the road network as a weighted graph.
- Calculate a suitable evacuation route.
- Simulate changes in road conditions.
- Update affected road weights or availability.
- Recalculate an alternate route.
- Display the resulting route through the web interface.
The project demonstrates the practical application of Data Structures,
Algorithms, and Object-Oriented Programming in C++ to an emergency
evacuation scenario.
👥 Team
Team Name: COGNITRIX
Team Members
- Agrima Pant — Team Lead
- Madhav Goel
- Sneha Verma
📚 References
1. Horowitz, E., Sahni, S. — Fundamentals of Data Structures and
   Algorithms.
2. Object-Oriented Programming with C++ — Course Material.
3. Dijkstra's Algorithm — Reference Material.
4. Cai, Z., Wang, T., Mi, Q., Su, X., Guo, L., & Ding, Z. (2023).
   Dynamic Weighted Road Network Based Multi-Vehicles Navigation and
   Evacuation.
5. Pang, M.-b., Ren, S.-s., & Zhang, J.-j. (2013).
   Selecting Emergency Evacuation Routes in Urban Dynamic Traffic
   Network.
