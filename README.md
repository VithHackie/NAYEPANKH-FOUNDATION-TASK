# 🕊️ NayePankh Foundation - NGO Management Platform

![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
![Vite](https://img.shields.io/badge/Vite-B73BFE?style=for-the-badge&logo=vite&logoColor=FFD62E)
![Firebase](https://img.shields.io/badge/firebase-ffca28?style=for-the-badge&logo=firebase&logoColor=black)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)

A modern, fast, and secure web application built to streamline operations, manage volunteers, and track donations for the NayePankh Foundation.

---

## 📊 Project Report: Executive Summary
**Project Name:** NayePankh Foundation Management Task  
**Tech Stack:** React.js, Vite, Node.js, Express, MongoDB/Firebase (Backend-as-a-Service)  
**Objective:** To digitalize and automate the workflow of the NayePankh Foundation, transitioning from manual tracking to a centralized digital ecosystem. 

**Summary of Achievements:**
1. **Frontend Optimization:** Scaffolded using Vite + React, achieving sub-second hot-module reloading and an optimized production build.
2. **User Management:** Implemented secure role-based access control (RBAC) ensuring that public users, volunteers, and admins have distinct, secure interactions with the platform.
3. **Data Centralization:** Migrated conceptual local data to a scalable, cloud-hosted database, allowing for real-time updates regarding donation drives and volunteer registrations.
4. **Administrative Oversight:** Developed a dedicated Admin Dashboard to visualize key metrics, manage incoming messages, and oversee NGO activities without requiring technical database knowledge.

---

## ✨ Features
* **Lightning Fast UI:** Powered by Vite and React.
* **Responsive Design:** Fully accessible on mobile, tablet, and desktop devices.
* **Volunteer Onboarding:** Interactive forms for new volunteers to sign up and get involved.
* **Donation Tracking:** Secure portals outlining 80G tax exemption details and donation tracking.
* **Real-time Notifications:** Alerts for admin staff when new inquiries or crisis reports are submitted.

---

## ⚙️ Core Implementations & How They Work

### 1. Connect a Database
To ensure data persistence and real-time synchronization, the application connects to a cloud database (e.g., MongoDB Atlas or Firebase Firestore).
* **How it works:** * The frontend communicates with RESTful API endpoints (or direct BaaS SDKs).
  * Data such as user profiles, contact messages, and donation records are formatted into JSON and stored in scalable document collections.
  * We utilize environment variables (`.env`) to securely store connection strings, ensuring that database credentials are never exposed in the source code.
  * **Benefit:** Centralizes all NGO data, making it instantly accessible to authorized personnel across different locations (Kanpur, Ghaziabad, etc.).

### 2. Add Authentication
Security and data privacy are paramount for an NGO handling sensitive contributor and volunteer information.
* **How it works:**
  * Implemented using JSON Web Tokens (JWT) or OAuth providers (like Google Auth via Firebase).
  * **Registration/Login:** Users submit their credentials, which are hashed and verified against the database.
  * **Session Management:** Upon successful login, a secure token is generated and stored in the browser's local storage or HTTP-only cookies.
  * **Route Protection:** React Router DOM is used to create Private Routes. If a user tries to access a protected page without a valid token, they are immediately redirected to the login screen.

### 3. Create an Admin Dashboard
The operational heart of the application. It provides the foundation's leaders with a bird's-eye view of all activities.
* **How it works:**
  * **Role-Based Access:** Only users with an `admin` flag in the database can access the `/admin` route.
  * **Data Aggregation:** The dashboard fetches data across multiple collections to display statistics: Total Volunteers, Recent Donations, Pending Inquiries.
  * **Interactive Tables:** Admins can view messages submitted through the public "Contact Us" form, mark them as read, or reply directly.
  * **Content Management:** Allows admins to post new campaigns or update the "News & Recognition" section dynamically without changing the code.

---

## 🚀 How the Application Works (User Flow)

1. **Public Discovery:** A visitor lands on the homepage, learns about the NayePankh Foundation's mission, and navigates through the lightweight SPA (Single Page Application).
2. **Interaction:** The user decides to volunteer or ask a question. They fill out a form on the site.
3. **Data Transmission:** The React frontend captures the form data, sanitizes it, and sends a POST request to the backend.
4. **Storage & Alert:** The database stores the inquiry. An automated trigger updates the Admin Dashboard.
5. **Admin Action:** An administrator logs in (Authentication), navigates to the secure Admin Dashboard, reviews the centralized database records, and contacts the new volunteer.

---

## 💻 Local Setup & Installation

To run this project locally on your machine:

```bash
# 1. Clone the repository
git clone [https://github.com/VithHackie/NAYEPANKH-FOUNDATION-TASK.git](https://github.com/VithHackie/NAYEPANKH-FOUNDATION-TASK.git)

# 2. Navigate into the directory
cd NAYEPANKH-FOUNDATION-TASK

# 3. Install dependencies
npm install

# 4. Set up environment variables
# Create a .env file in the root and add your Database URI and Auth secrets.
# Example: VITE_DB_CONNECTION_STRING=your_connection_string

# 5. Start the Vite development server
npm run dev
