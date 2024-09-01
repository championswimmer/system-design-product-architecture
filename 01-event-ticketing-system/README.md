# Event Ticketing System 
Like BookMyShow / Ticket Master 

## Requirements 

```
Functional Requirements: 
1. Events can be created 
2. Users can search for events 
3. Users can see seat availability for events 
4. Users can book tickets at the event 
--- 
5. See past bookings

Non-Functional Requirements: 
1. Should be able to handle 10M~100M users 
2. Should handle popular events (10M+ users trying to book it)
3. High availability of event search 
4. Consistent event booking (same seat not allocated to multiple people)
```

## Approximations 

```
Approximations 

Users: 100M 
DAU: 10M 
Peak Event Booking: 10M 
Searches / User: 10

100M / 10000 = ~1000 QPS
```

## Entities 

```
Entities: 

Events 
- id
- name 
- date/time
- seats_left

Users 
- id
- email 

Seats 
- event_id
- seat_number 
- status: (empty/blocked/booked)
- ttl 

Tickets 
- event_id
- seat_number
- user_id
```

## APIs

```
APIs 

GET /events/?name={}&from=&to=
<- event[]

GET /events/{id}/seats 
<- seat[]

POST /tickets 
🔒 {auth token, booking token}
-> {event, seat} 
```

## Design 

<img width="742" alt="image" src="https://github.com/user-attachments/assets/d7a19b5c-0ad9-45b5-b1b5-ff4b553ae127">


