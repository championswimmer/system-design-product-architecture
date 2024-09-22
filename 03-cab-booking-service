# Product Architecture : Cab Booking Service (eg: Uber) 

## Requirements 

```
Product Requirements 

Functional
- see fares for a trip 
- book a ride for a trip
- drivers get trip notifications
    - they can accept it
----------
- different types of cabs
- multi-point-trips
- payment gateways


Non-Functional
- high availability: fares, driver locations
- consistency: driver <> trip allocations
- scale: NYC/LON: 5M rides/day, peak: 1M/min
----------
- security, privacy 
```

## Entities

```
Entities: 

Rider 

Drivers 

Trip 
    - from
    - to
    - time
    - fare
    - valid_till
    - state: created/in_progress/finished

LocationPing
    - driver_id
    - lat/lng
    - timestamp 
    - trip_id? 
```

## APIs 

```
APIs 

get fare
    GET /fare/?from=<Lat,Lng>&to=<Lat,Lng>

create trip
    POST /trips
        {from, to}

accept/reject trips
    POST /trips/{tripid}/accept

update location (heartbeat; 10s)
    POST /location
        <LocationPing>
```

## Design 

