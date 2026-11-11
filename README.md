# Salon Appointment Scheduler

A relational database project developed as part of the **Relational Database Certification** from [freeCodeCamp](https://www.freecodecamp.org/).

This project focuses on building a salon appointment system using **PostgreSQL**, along with an interactive **Bash script** to manage customers and book appointments.

---

## Project Overview

The database stores information about salon customers, the services offered, and the appointments that have been booked.

A Bash script (`salon.sh`) displays a list of available services, asks the user to choose one, and then collects the customer's phone number and preferred appointment time. If the customer is not yet registered, the script also asks for their name and adds them to the database automatically.

---

## Technologies Used

| Technology | Purpose |
|------------|---------|
| **PostgreSQL** | Relational database management system |
| **SQL** | Database creation, table relationships, queries, and data manipulation |
| **Bash** | Interactive command-line scripting |
| **Linux Terminal** | Running scripts and database commands |

---

## Database Structure

The database is named `salon` and consists of three main tables:

- **`customers`** – Stores `customer_id` (primary key), `phone` (unique), and `name`.
- **`services`** – Stores `service_id` (primary key) and the service `name`.
- **`appointments`** – Stores `appointment_id` (primary key), the appointment `time`, and foreign keys `customer_id` and `service_id` linking to the other two tables.

The tables are connected using **primary keys** and **foreign keys** to maintain relational integrity.

---

## Features

- Display a numbered list of available services from the database.
- Re-prompt the user when an invalid service is selected.
- Look up customers by phone number.
- Register new customers automatically when the phone number is not found.
- Book an appointment by linking a customer, a service, and a time.
- Show a confirmation message after the appointment is saved.

---

## Repository Structure

| File | Description |
|------|-------------|
| `salon.sh` | Bash script that runs the interactive appointment scheduler |
| `salon.sql` | SQL dump used to create the database, tables, and initial data |

---

## How to Run

1. **Clone this repository:**

```bash
   git clone https://github.com/khadziq059/salon.git
```

2. **Navigate to the project directory:**

```bash
   cd salon
```

3. **Restore the database from the SQL file:**

```bash
   psql -U postgres < salon.sql
```

4. **Make the Bash script executable:**

```bash
   chmod +x salon.sh
```

5. **Run the script:**

```bash
   ./salon.sh
```

---

## Example Usage

```text
~~~~~ MY SALON ~~~~~

Welcome to My Salon, how can I help you?

1) cut
2) color
3) perm
4) style
5) trim

What is your phone number?
555-555-5555

I don't have a record for that phone number, what's your name?
Fabio

What time would you like your cut, Fabio?
10:30
