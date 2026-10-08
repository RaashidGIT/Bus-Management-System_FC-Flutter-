```markdown
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

**2. Core Processes (DFD Level 1)**
The system branches into three main processes based on user roles:
* **Search & Tracking (Normal & Special Users):** Users input search locations to query the database and retrieve bus details, schedules, and map coordinates.
* **Availability Management (Special Users):** Conductors provide real-time updates regarding bus location and availability to the database.
* **System Modification (Admin):** Admins supply the database with new bus details, employee profiles, and route adjustments.

**3. Detailed Sub-Processes (DFD Level 2)**
* **Process 2.0 (Special User Actions):** Special Users trigger four primary sub-processes: Providing Real-Time Location, Toggling Bus Availability, Providing Bus Employee Presence, and Submitting Bus Invoices to the database.
* **Process 3.0 (Admin Actions):** Admin privileges govern four distinct administrative sub-processes: Bus Registration, Employee Registration, Route Registration, and Updating/Modifying existing database records.

### Database Structure (ER Model)
The Firestore backend utilizes the following primary entities to organize data relationships:
* **Admin:** Stores `Username`, `Password`, and unique `Admin Id`.
* **Special User:** Stores conductor credentials including `Username`, `Password`, and `User Id`.
* **Bus Info:** Maintains fleet data like `Bus Id`, `Bus name`, assigned `Employees`, and `Availability` status.
* **Route & Schedule:** Links source (`From`) and destination (`To`) under `Route Id`, mapping directly to `Arrival Time` and `Departure Time` via `Schedule Id`.
* **Invoice:** Captures transactional data including `Invoice Id`, `Total Payment`, and `Date`.

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
