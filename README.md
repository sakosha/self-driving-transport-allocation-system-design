

# Problem
City's public transportation system experiences persistent inefficiencies, with overcrowded buses during peak hours and empty buses at off-peak times, causing dissatisfaction among passengers and poor utilization of resources.


Local administration is considering integrating self-driving (autonomous) vehicles into the existing public transit fleet to optimize resource allocation, reduce costs, and improve passenger experience


Design fleet management and optimization system that integrates self-driving buses into the city's existing transit infrastructure. Your solution should adjust vehicle allocation, routes, and scheduling (near real-time) based on demand, traffic conditions, and vehicle availability


P.S: remember about safety, clearly identify potential trade-offs and how your architecture resolve these challenges


## First of all: Non-goals
- change the way people pay for their commute
- trams, trolleybuses and especially underground are not really allocatable, as they are set in stone public transportation
- build self-driving cars hardware & software

## Assumption:
- as a starter we choose Almaty (~2 mil population, ~1.4 mil commuters)
- we look for 2 dates: 1 year, to spark Adoption & 5-10 years, to tackle continuous use
- collaboration w/ municipalities and not competing with them
- driver strikes are not in the scope
- we can put/use lots of cameras around the city to determine the traffic
- we are given lots of money to replace old buses, at least in batches

# func reqs:
- automatic deployment of vehicles
- ability to reassign vehicles due to spikes in traffic
- real-time monitoring of passenger load
- real-time monitoring of traffic situation
- ability to see all buses on the map
- load predefined route
- provide analytics of each route
- monitor the charge of vehicle
- synchronize with warehouse/repair station

# non-func reqs:
- latency: bus curr location has to be synchronized within 30 sec
- availability: our system has to be highly available (can be disputed)
- scalability: we should effortlessly handle thousands of vehicles & additional buses in our system
- safety: we have to comply with safety guidelines of ISO 26262
- obey the law/compliance w/ laws of the city/country.
- security
- maintainable