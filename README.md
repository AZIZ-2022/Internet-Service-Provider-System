# 🌐 City Broadband: Internet Service Provider System

A web portal for an internet service provider. Customers can register, browse the available broadband packages, subscribe to a plan, pay bills, and raise complaints, all from one account.

This repository contains the **Customer module** of the system.

---

## 🔄 How It Works

```
Register → Login → Browse available packages → Subscribe to a plan
      → Pay the bill (bKash / Nagad) → Billing history is recorded
      → Raise a complaint if there is a problem → Track complaint history
      → Unsubscribe when the plan is no longer needed
```

---

## ✨ Functionality

### 1. Registration & Login
- Register with name, email, password, phone number, address, and a profile picture
- Validation on both the browser and the server:
  - Name: letters and spaces only
  - Email: valid format
  - Phone: exactly 11 digits
  - Password: minimum length with a matching confirmation
  - Profile picture is required
- Login with email and password; the session keeps the customer signed in
- Logout ends the session

### 2. Browse Internet Packages
- Dashboard lists every available package with its ID, speed, price, and description
- One click on **Subscribe** opens the plan details

### 3. Subscriptions
- Subscribe to a package after reviewing its speed, price, and description
- **Subscribed Plans** page shows all plans the customer has taken, each with a subscription ID
- From each plan the customer can **Pay Bill** or **Unsubscribe**
- Unsubscribing asks for confirmation and removes the plan

### 4. Billing & Payments
- Pay a bill for a subscribed plan using **bKash** or **Nagad**
- Payment form validates the 11-digit account number and the password
- Every payment is saved in the billing history with plan, amount, payment method, and account number
- **Billing History** page shows past payments

### 5. Complaints
- Submit a complaint describing the issue
- **Complaint History** page lists all complaints raised by the logged-in customer

### 6. Profile Management
- View profile with name, phone, address, and picture
- Update name, phone, address, and profile picture

---

## 🖥️ Pages

| Page | Purpose |
|------|---------|
| `home.php` | Landing page with Login and Register buttons |
| `CRegistration.php` | Customer registration |
| `CustomerLogin.php` | Customer login |
| `CustomerDashboard.php` | Available packages |
| `subscribed_plans.php` | Confirm a subscription |
| `subscriptions.php` | The customer's subscribed plans |
| `CustomerBilling.php` | Pay a bill |
| `CusBillHistory.php` | Billing history |
| `unsubscribe.php` | Confirm unsubscribing |
| `CustomerComplaints.php` | Raise a complaint |
| `CustomerComplaintHistory.php` | Complaint history |
| `Cusprofile.php`, `update_profile.php` | View and edit profile |
| `Existing_service.php` | List of existing services |

---

## 🗃️ Database

MySQL database named `broadband service management system` with these tables:

| Table | Stores |
|-------|--------|
| `customer_reg` | Customer account: name, email, password, phone, address, profile picture |
| `service` | Packages: ID, speed, price, description |
| `subscribed_plans` | Customer subscriptions: subscription ID, customer email, plan details |
| `billing_history` | Payments: plan, price, payment method, account number, email |
| `complaint_history` | Complaints: ID, description, customer email |

---

## 🛠️ Tech Stack

- **Backend:** PHP with a simple MVC structure
- **Database:** MySQL (MySQLi)
- **Frontend:** HTML, CSS, and JavaScript form validation

---

## 📁 Project Structure

```
Customer/
├── model/       # db.php: database connection and all queries
├── control/     # PHP controllers: registration, login, subscriptions, billing, complaints, profile
├── view/        # PHP pages shown to the customer
├── styles/      # CSS for each page
├── js/          # Client-side form validation
└── uploads/     # Customer profile pictures
```

---

## 🚀 Getting Started

1. Install a local PHP and MySQL stack such as XAMPP, then clone the project into the web root (`htdocs`):
   ```bash
   git clone https://github.com/AZIZ-2022/Internet-Service-Provider-System.git
   ```
2. Start **Apache** and **MySQL**.
3. In phpMyAdmin, create the database `broadband service management system` and the five tables listed above.
4. Add a few packages to the `service` table (speed, price, description) so customers have something to subscribe to.
5. Check the database host, username, and password in `Customer/model/db.php`.
6. Make sure the `Customer/uploads/` folder exists and is writable.
7. Open `http://localhost/Internet-Service-Provider-System/Customer/view/home.php`.

---

## 🗺️ Roadmap

- [ ] Admin panel to add packages, view customers, and answer complaints (the data layer for adding services and listing customers is already in `db.php`)
- [ ] Password hashing
- [ ] Bill due dates and automatic monthly invoices
- [ ] Complaint status and replies from support
- [ ] Upgrade or downgrade a plan without unsubscribing

---

## 👤 Author

**AZIZ-2022**: [GitHub](https://github.com/AZIZ-2022)
