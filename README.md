
#                              🎬 Movie Ticket Booking Management System

![Pega](https://img.shields.io/badge/Platform-Pega-blue)
![NIP](https://img.shields.io/badge/NIP-2026-green)
![Status](https://img.shields.io/badge/Status-Completed-success)
![Project](https://img.shields.io/badge/Project-Movie%20Ticket%20Booking-orange)

> A Pega-based application for managing movie ticket booking requests through availability checking, cost calculation, customer approval, booking execution, and confirmation.

---

## 📌 Project Overview

The **Movie Ticket Booking Management System** is developed using the **Pega Platform** as part of the **National Internship Program (NIP) 2026**.

The application manages the complete movie ticket booking process from submitting a booking request to final booking confirmation.

The system provides a structured workflow for:

- 🎬 Movie selection
- 📅 Show date and time
- 🎟️ Ticket quantity
- 💺 Seat availability
- 💰 Booking cost calculation
- 👤 Customer approval
- 🎫 Ticket booking
- 📧 Booking confirmation
- ⏱️ SLA management
- 🔀 Show-type based routing

---

# 🎯 Project Objective

The main objective is to develop a workflow-based **Movie Ticket Booking Management Application** using Pega.

The system helps users:

1. Submit movie ticket requests.
2. Check show availability.
3. Calculate booking cost.
4. Confirm or cancel booking requests.
5. Maintain movie and show information.
6. Review booking details.
7. Process ticket booking.
8. Send booking confirmation.
9. Manage booking SLA.
10. Route requests based on show type.

---

# 🏗️ Application Details

| Field | Details |
|---|---|
| Project Name | Movie Ticket Booking Management System |
| Application Name | Ticketing and Booking |
| Case Type | Movie Ticket Request |
| Platform | Pega Platform |
| Pega Version | 25.1.3 |
| Program | National Internship Program (NIP) 2026 |
| Developer | Dharaneeshwaran.M |
| College | VSB Engineering College, Karur |
| State | Tamil Nadu, India |
| Email | dharaneeshwaran091@gmail.com |
| Status | Completed ✅ |

---

# 👨‍💻 Developer Details

### Dharaneeshwaran.M

**College:** VSB Engineering College, Karur  
**Email:** dharaneeshwaran091@gmail.com  
**State:** Tamil Nadu, India

---

# 🔄 Application Workflow

```text
                ┌──────────────────────┐
                │  Booking Request     │
                └──────────┬───────────┘
                           │
                           ▼
                ┌──────────────────────┐
                │ Availability Check   │
                └──────────┬───────────┘
                           │
                    Seats Available?
                       /          \
                     Yes           No
                      │             │
                      ▼             ▼
             ┌──────────────┐   Request
             │ Cost         │   Cannot
             │ Calculation  │   Proceed
             └──────┬───────┘
                    │
                    ▼
             ┌──────────────┐
             │ Customer     │
             │ Approval     │
             └──────┬───────┘
                    │
              Confirm / Cancel
                /          \
          Confirm           Cancel
             │                │
             ▼                ▼
     ┌──────────────┐      Closed
     │ Booking      │
     │ Execution    │
     └──────┬───────┘
            │
            ▼
     ┌──────────────┐
     │ Booking      │
     │ Confirmation │
     └──────────────┘
````

---

# 📋 Case Type

## Movie Ticket Request

The main case type used in the application is:

**Movie Ticket Request**

The case manages the complete movie ticket booking lifecycle.

---

# 🧩 Case Stages

The application contains four major stages.

### 1️⃣ Booking Request

The customer submits the movie ticket booking request.

Details include:

* Movie Name
* Show Date
* Show Time
* Number of Tickets

---

### 2️⃣ Availability

The system checks whether sufficient seats are available for the selected show.

The stage maintains:

* Seat Availability Status
* Available Seats Count

The request proceeds only when seats are available.

---

### 3️⃣ Approval

The customer reviews the booking information and confirms or cancels the request.

The system maintains:

* Booking Status
* Confirmation decision

Possible outcomes:

```text
Confirm → Continue Booking
Cancel  → Close Request
```

---

### 4️⃣ Booking Execution

The booking is processed after customer confirmation.

The system generates:

* Seat Numbers
* Ticket ID
* Booking Confirmation Status

---

# ⭐ Key Features

## 🎬 Movie Ticket Request

Customers can submit movie ticket requests by providing:

* Movie name
* Show date
* Show time
* Number of tickets

---

## 💺 Seat Availability

The application checks seat availability before continuing the booking process.

The system maintains:

**Seat Availability Status**

and

**Available Seats Count**

---

## 💰 Booking Cost Calculation

The booking cost is calculated automatically.

### Formula

```text
Total Cost = Ticket Price × Number of Tickets
```

This avoids manual calculation and improves booking accuracy.

---

## 👤 Customer Approval

The customer can review the booking details before the booking is executed.

The customer can:

```text
Confirm
   ↓
Continue Booking

OR

Cancel
   ↓
Close Request
```

---

## 🎫 Ticket Booking

After approval, the system processes the ticket booking.

The booking execution includes:

* Seat Numbers
* Ticket ID
* Booking Confirmation Status

---

## 📧 Booking Confirmation

After successful booking resolution, a correspondence rule is used to send booking confirmation.

The confirmation contains information such as:

* Case details
* Movie name
* Show details
* Seat information
* Booking cost
* Confirmation status

---

# ⏱️ SLA Management

The application defines a Service Level Agreement for booking requests.

| SLA           | Value             |
| ------------- | ----------------- |
| Goal          | 1 Day             |
| Deadline      | 2 Days            |
| Breach Action | Priority Increase |

If the booking request exceeds the defined SLA, the case priority is increased.

---

# 🔀 Show Type Routing

The application routes booking requests based on the **Show Type**.

### Premium / Special Show

Requests are routed to:

```text
PremiumShowQueue
```

### Standard Show

Requests are routed to:

```text
StandardShowQueue
```

The routing can be implemented using a **When Rule** or **Decision Table**.

---

# 🗃️ Data Objects

The application uses reusable data objects for managing movie and show information.

## 🎬 Movie

Movie-related information includes:

* Movie Name
* Genre

---

## 🕐 Show

Show-related information includes:

* Movie Name
* Show Date
* Show Time
* Seat Capacity

The show information is linked to the booking case.

---

# 👥 Personas

The application supports different users involved in the booking process.

### 👤 Customer

The customer:

* Submits booking requests
* Reviews booking details
* Confirms booking
* Cancels booking

### 👨‍💼 Booking Agent

The booking agent handles:

* Availability
* Booking processing
* Ticket execution
* Booking management

---

# 📖 User Stories

## US-001 — Submit Movie Ticket Request

The user can submit a movie ticket booking request.

### Fields

* Movie Name
* Show Date
* Show Time
* Number of Tickets

The system validates the entered information.

---

## US-002 — Check Show Availability

The system checks show availability during the Availability stage.

### Fields

* Seat Availability Status
* Available Seats Count

The booking proceeds only when seats are available.

---

## US-003 — Calculate Booking Cost

The system automatically calculates the booking cost.

### Formula

```text
Total Cost = Ticket Price × Number of Tickets
```

The calculation is implemented using a business rule.

---

## US-004 — Confirm Booking Request

The customer reviews the request during the Approval stage.

The customer can:

```text
Confirm
```

or

```text
Cancel
```

The system updates the Booking Status accordingly.

---

## US-005 — Maintain Movie and Show Data

Reusable Movie and Show data objects are maintained.

### Movie

* Movie Name
* Genre

### Show

* Movie Name
* Show Date
* Show Time
* Seat Capacity

The selected movie and show are linked to the booking case.

---

## US-006 — Review Booking Details

The customer can review the booking details before confirmation.

The details include:

* Movie Name
* Show Timing
* Number of Tickets
* Total Cost

---

## US-007 — Process Ticket Booking

The booking is processed during the Booking Execution stage.

The system maintains:

* Seat Numbers
* Ticket ID
* Booking Confirmation Status

---

## US-008 — Notify Booking Confirmation

A correspondence rule is triggered when the booking is resolved.

The notification contains:

* Case details
* Movie name
* Show details
* Seat information
* Total cost
* Booking confirmation

---

## US-009 — Define Booking SLA

The booking case has a defined SLA.

```text
Goal     → 1 Day
Deadline → 2 Days
```

When the SLA is breached, the case priority increases.

---

## US-010 — Route by Show Type

The system routes requests according to Show Type.

```text
Premium / Special
        ↓
PremiumShowQueue

Standard
        ↓
StandardShowQueue
```

The routing can be configured using:

* When Rule
* Decision Table

---

# 🛠️ Technology Stack

| Technology                 | Usage                     |
| -------------------------- | ------------------------- |
| Pega Platform              | Application Development   |
| App Studio                 | Application Configuration |
| Case Management            | Booking Workflow          |
| Business Rules             | Cost Calculation          |
| Decision Table / When Rule | Show Routing              |
| Correspondence             | Booking Notification      |
| SLA                        | Booking Time Management   |
| Data Objects               | Movie and Show Management |

---

# 📁 Project Structure

The GitHub repository contains the Pega application export.

```text
Movie-Ticket-Booking-Pega-NIP-2026/
│
├── README.md
│
└── Pega Application Export/
    └── Ticketing_2_010101_20260903T183947_GMT.zip
```

> The Pega export ZIP should be kept as a ZIP file. Do not extract the Pega application archive before uploading it to GitHub.

---

# 📦 Pega Application Export

The project has been exported from the Pega environment as a Pega application archive.

The export contains application metadata and Pega rules/schema files required for the application.

Example contents:

```text
META-INF/
│
├── MANIFEST.MF
│
├── Application.xml
│
├── application.properties
│
├── Ticketing_*_schema.jar
│
└── Ticketing_*_rules.jar
```

---

# 🚀 Getting Started

## Step 1 — Obtain the Repository

Clone the repository:

```bash
git clone <YOUR-GITHUB-REPOSITORY-URL>
```

---

## Step 2 — Download the Pega Export

Download the Pega application export ZIP from the GitHub repository.

---

## Step 3 — Import into Pega

Use the Pega application import functionality to import the exported application into a compatible Pega environment.

---

## Step 4 — Open the Application

Open:

```text
Application: Ticketing and Booking
```

---

## Step 5 — Open the Case Type

Open:

```text
Case Type: Movie Ticket Request
```

---

# 🧪 Testing

The following functionality should be verified:

### Booking Request

* [x] Movie name validation
* [x] Show date validation
* [x] Show time validation
* [x] Number of tickets validation

### Availability

* [x] Seat availability check
* [x] Available seat count

### Cost Calculation

* [x] Ticket price
* [x] Number of tickets
* [x] Total cost calculation

### Approval

* [x] Customer review
* [x] Confirm option
* [x] Cancel option
* [x] Booking status

### Booking Execution

* [x] Seat numbers
* [x] Ticket ID
* [x] Confirmation status

### Notification

* [x] Booking confirmation
* [x] Correspondence rule

### SLA

* [x] 1-day goal
* [x] 2-day deadline
* [x] Priority increase on breach

### Routing

* [x] PremiumShowQueue
* [x] StandardShowQueue

---

# 📸 Screenshots

Screenshots of the following Pega screens can be added here:

### Application

```text
Add Pega Application Screenshot
```

### Case Type

```text
Add Movie Ticket Request Screenshot
```

### Booking Request

```text
Add Booking Request Screenshot
```

### Availability

```text
Add Availability Screenshot
```

### Approval

```text
Add Approval Screenshot
```

### Booking Execution

```text
Add Booking Execution Screenshot
```

### Data Objects

```text
Add Movie and Show Data Object Screenshots
```

### Workflow

```text
Add Workflow Screenshot
```

---

# 📊 Project Status

## 🟢 COMPLETED

The **Movie Ticket Booking Management System** has been completed as part of the **National Internship Program (NIP) 2026**.

### Completed Components

* ✅ Pega application created
* ✅ Movie Ticket Request case type configured
* ✅ Booking Request stage configured
* ✅ Availability stage configured
* ✅ Approval stage configured
* ✅ Booking Execution stage configured
* ✅ Movie data object configured
* ✅ Show data object configured
* ✅ Booking cost calculation configured
* ✅ Customer approval flow configured
* ✅ Ticket booking process configured
* ✅ Booking confirmation configured
* ✅ Correspondence configured
* ✅ Booking SLA configured
* ✅ Show-type routing configured
* ✅ Pega application exported
* ✅ GitHub repository prepared

---

# 🎓 Internship Details

| Field     | Details                                                             |
| --------- | ------------------------------------------------------------------- |
| Program   | National Internship Program (NIP) 2026                              |
| Platform  | Pega Platform                                                       |
| Project   | Movie Ticket Booking Management Application                         |
| Developer | Dharaneeshwaran.M                                                   |
| College   | VSB Engineering College, Karur                                      |
| Email     | [dharaneeshwaran091@gmail.com](mailto:dharaneeshwaran091@gmail.com) |
| State     | Tamil Nadu, India                                                   |
| Status    | Completed ✅                                                         |

---

# 🎯 Project Outcome

The project demonstrates how **Pega Case Management** can be used to automate a complete movie ticket booking workflow.

The application integrates:

```text
Case Management
       +
Data Objects
       +
Business Rules
       +
Decision Logic
       +
Approval
       +
SLA
       +
Correspondence
       +
Routing
```

This provides a structured and automated approach to movie ticket booking management.

---

# 📌 Repository Information

**Repository Name:**

```text
Movie-Ticket-Booking-Pega-NIP-2026
```

**Project:** Movie Ticket Booking Management System

**Application:** Ticketing and Booking

**Case Type:** Movie Ticket Request

**Program:** National Internship Program 2026

---

# 👨‍💻 Author

**Dharaneeshwaran.M**

🎓 VSB Engineering College, Karur
📧 [dharaneeshwaran091@gmail.com](mailto:dharaneeshwaran091@gmail.com)
🇮🇳 Tamil Nadu, India

---

# 📄 License

This project was developed for educational and internship purposes as part of the **National Internship Program (NIP) 2026**.

---

## ⭐ Project Status

**Completed — NIP 2026 ✅**

````

### Important

For your GitHub repository, keep these files:

```text
Movie-Ticket-Booking-Pega-NIP-2026
│
├── README.md
│
└── Ticketing_2_010101_20260903T183947_GMT.zip
