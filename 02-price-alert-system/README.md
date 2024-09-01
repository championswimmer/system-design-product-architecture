# Flight Price Alert System 

## Requirements 

```
Functional Requirements

- users can set price alerts 
    - for a particular route (to, from) 
    - for a given date of travel 
- send an alert to the user if price falls below
  last price they have seen 
- users can setup alerts for upto 90 days

Non-Functional Requirements

- 10M users, 0.5M DAU (0.5M alerts set/day)
- 1000P2 - routes possible 
- check for prices every 12 hrs
- alerts can be queued for upto 30min

```

## Entities 

```
Entities 

Users 
- id, name
- email, phno 

Journey 
- to
- from
- date
- update_freq (hr, day)

Journey_Price
- journey_id  (eg: LHR -> NYC, 3rd Dec)
- price
- date_time 

User_Alerts 
- user_id
- journey_id (eg: LHR -> NYC, 3rd Dec)
- min_price
- channel (email/sms)
```

## System Diagram

<img width="1133" alt="image" src="https://github.com/user-attachments/assets/23da7cf3-672d-4fe9-b44e-0fcd406279b9">
