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
