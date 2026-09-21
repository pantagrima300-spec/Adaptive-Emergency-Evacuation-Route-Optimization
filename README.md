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
