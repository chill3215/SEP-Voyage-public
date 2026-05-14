# SEP-Voyage-public

## Live Demo
[Open SEP Voyage](https://sep-voyage.vercel.app/)

This repository does not contain the source code of the application.  
It only provides the public demo link and a README instruction guide for testing the application.

---

# Introduction

SEP Voyage is a ride-sharing and ride-simulation platform that allows customers and drivers to interact in real time. The application supports:

- Ride request creation
- Interactive route planning
- Real-time ride simulation
- Live synchronization between customer and driver
- Multiple stopovers
- Live route modifications
- Wallet and payment simulation
- Driver statistics
- Ride history
- Live chat

This guide explains the recommended testing flow and the important notes for each function.

---

# Important Testing Setup (Read First)

Some core features require real-time synchronization between customer and driver.

## Recommended Setup for testing
Use either:
- two separate browsers
- OR one normal browser window + one incognito/private window

This allows testing with:
- one customer account
- one driver account

simultaneously.

---

## Important Notes

### Backend Cold Start
When opening the demo for the first time after inactivity, the backend server may need time to start. As a result, first requests may take longer than usual, please wait a short moment.

---

# 1. Registration and Login

1. Open the demo link.
2. Register a new account or log in with an existing account.
3. After successful login credential validation, a 2FA code is sent via email.
4. Verification:
   Users can:
- enter the received 2FA code (2FA code may be sent to spam folder of the email)
- or use the testing supercode:
```text
supercode123
```
---

# 2. Wallet System 

Customers can:
- open the user profile
- navigate to the wallet section
- recharge balance
The current balance is visible in the user profile

---

# 3. Interactive Map and Route Planning

The application provides an interactive map with zooming, dragging, marker placement, route visualization, route reset

1. Select a map action:
   - Add Start, Add Destination, Add Stopover (optional)
2. Click on the map to place markers.
3. Click **“Strecke anzeigen”**

---

### Invalid Configurations
The application displays warning messages if:
- start point is missing
- destination is missing
- multiple start points are added
- multiple destinations are added

---

# 4. Creating Ride Requests for Customer

On the customer browser: 
1. Choose input method: current location, address, POI, coordinates
2. Enter: start location, destination, add stopovers
3. Select desired vehicle class.
---

# 5. Available Ride Requests for Driver and Ride Offers for Customer

Drivers can 
- open **“Liste der verfügbaren Fahrten”**
- accept ride requests
- withdraw offers later if necessary

Customers can:
- open **“Offene Fahrangebote”**
- accept offers
- reject offers

---

# 6. Ride Simulation and Real-Time Synchronization
After a customer accepts a driver offer, both users share the same ride simulation session. For testing, open the **“Fahrtsimulation”** on browsers for customer and driver simultaneously

### Simulation Controls:
- Both parties can start, pause, resume the simulation.
### Live Route Changes During Simulation:
- During simulation, customers can modify the ride in real time: change destination, add stopovers, remove stopovers
### Speed Adjustment:
- Simulation duration can be adjusted 
### Live Chat:
- Both users can send messages, edit messages, delete messages. Messages can be marked as read. After being marked as read, messages can no longer be edited nor deleted (Editing input for message may still appear, but changes are no longer applied)
### Ride Completion:
- After reaching the destination:
  + customer balance decreases
  + driver balance increases automatically
  + both customer and driver can rate each other

---

# 7. Ride History

Completed rides appear under **“Fahrhistorie”**

# 8. Driver Statistics and Leaderboard

## Driver Statistics

- Drivers can open **“Meine Statistiken”**
- Available statistics: earnings, total distance, total driving time, average rating

## Driver Leaderboard

- The leaderboard displays information about statistics total distance, average rating, total driving time, completed rides, earned money

