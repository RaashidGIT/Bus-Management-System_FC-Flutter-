# NextBus 🚌 - Bus Management System

NextBus is a cross-platform Bus Management System developed using Flutter to streamline public transportation for passengers, conductors, and administrators. The application provides real-time bus tracking, digital invoicing, and dynamic schedule management to solve challenges like overcrowding, unpunctuality, and poor data integrity in traditional transit systems.

## 🌟 Key Features

### 👥 Passengers (Normal Users)
* **Smart Search:** Search for available buses by entering source and destination routes.
* **Live Tracking:** Track the real-time location of buses on an interactive map powered by Mapbox.
* **Schedule & Availability:** View accurate bus schedules and check live bus availability (e.g., active/inactive status) before heading to the stop.

### 🎫 Bus Employees (Special Users / Conductors)
* **Real-time Status Updates:** Toggle bus availability and update employee presence data.
* **Digital Invoice Management:** Calculate daily ticket sales, total passengers, and upload digital invoices directly to the central database, eliminating manual paper records.

### 🛡️ Administrators
* **Centralized Dashboard:** A dedicated interface for overseeing operations.
* **Fleet & Staff Management:** Register new buses, define specific routes, and create secure accounts for bus employees.
* **Data Modification:** Update existing bus instances, route timings, and employee details seamlessly.

---

## 🛠️ Tech Stack

* **Frontend:** Flutter & Dart
* **Backend Database:** Firebase Cloud Firestore (NoSQL)
* **Authentication:** Firebase Authentication (Role-based access)
* **Mapping Service:** Mapbox API
* **Version Control:** Git

---

## 🏗️ System Architecture & Data Flow

The system employs a strict role-based architecture to manage data securely. Below is the breakdown of the system's Data Flow Diagrams (DFD) and Entity-Relationship (ER) models.

### Data Flow Diagrams (DFD)

**1. Context Level (DFD Level 0)**
The top-level architecture demonstrates how three primary entities interact with the central database:
* **Normal Users** and **Special Users** hold "View" privileges to fetch data from the Bus Management Database.
* **Admins** maintain full "Control" privileges over the Bus Management Database.

* <img width="797" height="362" alt="image" src="https://github.com/user-attachments/assets/6489bbce-185f-4071-bc59-61e63193aae7" />


**2. Core Processes (DFD Level 1)**
The system branches into three main processes based on user roles:
* **Search & Tracking (Normal & Special Users):** Users input search locations to query the database and retrieve bus details, schedules, and map coordinates.
* **Availability Management (Special Users):** Conductors provide real-time updates regarding bus location and availability to the database.
* **System Modification (Admin):** Admins supply the database with new bus details, employee profiles, and route adjustments.

<img width="762" height="392" alt="image" src="https://github.com/user-attachments/assets/c215ef06-fd81-4d03-bb70-77cfc5adaabb" />


**3. Detailed Sub-Processes (DFD Level 2)**
* **Process 2.0 (Special User Actions):** Special Users trigger four primary sub-processes: Providing Real-Time Location, Toggling Bus Availability, Providing Bus Employee Presence, and Submitting Bus Invoices to the database.
* **Process 3.0 (Admin Actions):** Admin privileges govern four distinct administrative sub-processes: Bus Registration, Employee Registration, Route Registration, and Updating/Modifying existing database records.

* <img width="726" height="371" alt="image" src="https://github.com/user-attachments/assets/d8ff0f28-33f7-4e72-a013-edc7e6d2e475" />
* <img width="671" height="335" alt="image" src="https://github.com/user-attachments/assets/76d131b2-ec24-494f-a58b-3764b72c4a0e" />


### Database Structure (ER Model)
The Firestore backend utilizes the following primary entities to organize data relationships:
* **Admin:** Stores `Username`, `Password`, and unique `Admin Id`.
* **Special User:** Stores conductor credentials including `Username`, `Password`, and `User Id`.
* **Bus Info:** Maintains fleet data like `Bus Id`, `Bus name`, assigned `Employees`, and `Availability` status.
* **Route & Schedule:** Links source (`From`) and destination (`To`) under `Route Id`, mapping directly to `Arrival Time` and `Departure Time` via `Schedule Id`.
* **Invoice:** Captures transactional data including `Invoice Id`, `Total Payment`, and `Date`.

* <img width="903" height="970" alt="image" src="https://github.com/user-attachments/assets/738dcaf0-2ecf-47c3-879e-893b2352c2c9" />

---

## Screenshots

**1. Home Page**
* <img width="337" height="607" alt="image" src="https://github.com/user-attachments/assets/0bcfd1f6-949d-4c3f-afde-7b2573279525" />

**2. Menu Screen**
* <img width="251" height="502" alt="image" src="https://github.com/user-attachments/assets/15461de0-cd1d-446e-9fe7-5153460aa1ca" />

**3. Bus Availability**
* <img width="250" height="502" alt="image" src="https://github.com/user-attachments/assets/46046a2a-aaa2-4e66-a400-cb0579ed22a5" />

**4. Bus Availability**
* <img width="250" height="502" alt="image" src="https://github.com/user-attachments/assets/46046a2a-aaa2-4e66-a400-cb0579ed22a5" />

**5. Location of the Bus**
* <img width="250" height="503" alt="image" src="https://github.com/user-attachments/assets/41bcd604-ca4c-4e32-91f7-ea92644df966" />

**6. Bus Location**
* <img width="252" height="495" alt="image" src="https://github.com/user-attachments/assets/4bb41341-6f3e-4dda-8097-2b70040e0707" />

**7. User Location**
* <img width="252" height="503" alt="image" src="https://github.com/user-attachments/assets/04b1d347-bb9b-493a-a900-2b58231fe7a1" />

**8. Login Page**
* <img width="248" height="498" alt="image" src="https://github.com/user-attachments/assets/c7cf0132-90d4-4696-8d94-c71169f36f0d" />

**9. Admin Page**
* <img width="245" height="497" alt="image" src="https://github.com/user-attachments/assets/25c2ef64-bc80-4b79-8cab-c083b7a54003" />

**10. Sign up new Bus**
* <img width="252" height="500" alt="image" src="https://github.com/user-attachments/assets/a7b3cc38-01ab-4558-a288-fb28d0a4e7b1" />

**11. Sign up new Bus 2**
* <img width="247" height="500" alt="image" src="https://github.com/user-attachments/assets/c3e2db1a-797b-4366-a7f6-96dccdefeb76" />

**11. Time**
* <img width="251" height="505" alt="image" src="https://github.com/user-attachments/assets/efef8db7-69dd-442c-824b-ff852940c3b0" />

**12. Bus Details**
* <img width="247" height="506" alt="image" src="https://github.com/user-attachments/assets/d2d54390-8fa5-4f8c-9f37-c98759cce772" />

**13. Invoice Management**
* <img width="250" height="505" alt="image" src="https://github.com/user-attachments/assets/457e4998-0d6f-49ef-a10f-4894736884dd" />

**13. Add New Invoice**
* <img width="252" height="503" alt="image" src="https://github.com/user-attachments/assets/d0aae7ac-470c-40f4-b3dd-6c130d032914" />

--- 

## 🚀 Getting Started

### Prerequisites
* Flutter SDK (Version 3.0.0 or higher recommended)
* Dart SDK
* Android Studio or VS Code[cite: 16]
* A Firebase Project configured with Authentication and Firestore

### Installation
1. **Clone the repository:**
   ```bash
   git clone [https://github.com/yourusername/NextBus.git](https://github.com/yourusername/NextBus.git)

```

2. **Navigate to the project directory:**
```bash
cd NextBus

```


3. **Install dependencies:**
```bash
flutter pub get

```

4. **Configure Mapbox & Firebase:**
* Add your Mapbox public access token to the designated mapping widget.

* Ensure your `google-services.json` (Android) and `GoogleService-Info.plist` (iOS) are placed in their respective root directories.


5. **Run the application:**
```bash
flutter run

```

## 📱 Minimum Device Requirements

* **Operating System:** Android 4.1 or above
* **RAM:** 4GB minimum
* **Storage:** 600MB minimum free space

```

```
