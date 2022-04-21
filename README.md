# Optimization of Bus-routes in Montréal

## Overview
Public transport is the backbone of cities which aspire at being accessible to all its residents and beyond. The Montreal Bus Network Problem aims to find the solutions in order to minimize the total number of buses k required to serve all the bus stops in the Montreal downtown area.

## Methodology
The problem is modelled as a Vehicle Routing Problem and solved using [Gurobi](https://www.gurobi.com).

### Data Collection
To obtain accurate information, we overlaid the bus stops data collected on STM on the Montreal’s road network provided by McGill library. We used OD Cost Matrix functionality in ArcMap for finding the shortest road distance between stops. The access to the latest road network data for Montreal was provided by McGill library. Since these were 8500 stops, this mapping generation took extensive time and generated a large .csv file of over 72 million records containing both time and distance mappings between stops, scope was limited to select bus-stops in Downtown.

### Modelling
This problem was modelled according to the mTSP approach [highlighted](https://www.sciencedirect.com/science/article/abs/pii/S0305048304001550). Additionally, constraints were added to:
- All buses to start from Bonaventure Station
- One bus to visit the stops along Vieux-Port de Montréal
- A single route must cover the direct route from St Antoine/ de la Cathédrale (53696) as it is the bus stop the nearest to the suburbs trains terminal to Decelles/ Queen Mary (51278) as it is near multiple large universities including HEC Montreal and Université de Montreal.

## Future Implementations
The project recommends the **minimum number of buses**, along with their **routes** to satisfy given constraints. 
Extensions can be made on the following:
- Including Customer demand
- Including maintenance costs & frequency for buses
- Increasing the scope of the project to include more bus-stops
- Incorporating time-windows for a route to cater for customer wait-times
- Incorporating real-time customer demand
