# ✈ Airline Data Management & Analysis using Power BI

## 📌 Problem Statement
The airline industry operates with numerous complexities, requiring effective data management and insights into flight schedules, passenger details, and ticketing systems.  
This project analyzes airline operations to improve efficiency and customer satisfaction.

---

##   Datasets Used
1. **Flight Information** – `FlightID`, `FlightNumber`, `Airline`, `Destination`, `Status`
2. **Passenger Information** – `PassengerID`, `FlightID`, `SeatNumber`
3. **Ticket Information** – `TicketID`, `FlightID`, `BookingStatus`

---

## 🎯 Objective
To analyze and visualize airline data for operational insights, passenger management, and ticket booking trends using **Power BI**.

---

## 🛠 Tasks & Deliverables

### **1. Data Preparation and Cleaning**
- Imported all datasets into Power BI using Power Query.
- Removed duplicates, handled missing values, standardized column formats.
- Changed data types where necessary.

---

### **2. Data Modeling **
- Established relationships based on **FlightID**:
  - Flight Information ↔ Passenger Information
  - Flight Information ↔ Ticket Information
- Set **One-to-Many** cardinality and ensured referential integrity.

---

### **3. Enhanced Data Insights **
- Created **Flight Quality** column:
  - `"Best"` if Status = `"On Time"`, else `"To Be Improved"`.
- Extracted numeric part of Flight Number using **Column from Examples**.

---

### **4. Calculations Using DAX **
- Key DAX Measures:
  ```DAX
  Cancelled Bookings =
  CALCULATE(COUNT(ticket_information[TicketID]),
            ticket_information[BookingStatus] = "Cancelled")

  Cancellation Rate = DIVIDE([Cancelled Bookings], [Total Tickets Booked])

  Total Destination = DISTINCTCOUNT(flight_information[Destination])
  Total Flights = COUNT(flight_information[FlightID])
  Total Operational Airlines = DISTINCTCOUNT(flight_information[Airline])
  Total Tickets Booked = COUNT(ticket_information[TicketID])

  
  Total Passengers = COUNT(passenger_information[FlightID])

### **5. Visualization & Interactivity (20 Marks)**

**Visuals Created:**
1. Passenger count by airline.
2. Ticket booking statuses (booked, cancelled, etc.).
3. Flights by airline and destination.

**Interactive Features:**
4. Slicers for Destination and Airline.
5. Airline-specific pages with navigation buttons.
6. Cards for quick views.

---

### **6. Final Dashboard & Power BI Service (20 Marks)**

**Actions Performed:**
1. Designed a final dashboard summarizing KPIs and visuals.
2. Configured Row-Level Security (RLS) for Airline A.
3. Scheduled data refresh at **5 PM daily** in Power BI Service.
4. Published the dashboard online.

---

## 📊 Tools & Technologies
1. Power BI Desktop  
2. Power Query  
3. DAX  
4. Power BI Service

  
