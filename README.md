# Event Buddy - Full Stack Event Booking System

Event Buddy is a full-stack, simplified version of an event booking platform where users can browse upcoming events and book their seats. It features a complete authentication system with distinct roles for regular users and administrators, a responsive frontend built with Next.js, and a robust RESTful API powered by NestJS.

This project was built as a technical test, fulfilling all specified requirements for both frontend and backend development.

---

# Project Sceenshoots

### Landing Page
![Image](https://github.com/user-attachments/assets/8f9526c3-649a-47c6-8fe8-8828168445ee)

### User Dashboard
![Image](https://github.com/user-attachments/assets/50c65d61-b6ee-4ab0-8c66-a6cf77bb8688)

### Admin Dashboard
![Image](https://github.com/user-attachments/assets/0b728e3d-d057-4390-badc-85afc6782929)

### Event Deatils As User
![Image](https://github.com/user-attachments/assets/7cec36c1-db0d-4a9a-a1fc-42e1fdf17082)

### Event Deatils As Admin
![Image](https://github.com/user-attachments/assets/e6540462-35c3-4ba5-8a01-d4ccb780166a)

### Event Create
![Image](https://github.com/user-attachments/assets/f903936d-ad06-4185-985a-1d499fac92f3)

### Event Edit
![Image](https://github.com/user-attachments/assets/44ed1a83-f506-46ba-8561-ffc147f44c9a)

### Sign Up
![Image](https://github.com/user-attachments/assets/c4d5c388-8c29-4b74-a99f-2901c1e24541)

### Sign Up
![Image](https://github.com/user-attachments/assets/8f5cee34-52cc-45a4-8ef7-577c29549bca)

---

# Key Features

The application is divided into three core functional areas:

### **User Functionality**
- **Event Discovery:** Browse paginated lists of upcoming and past events.
- **Detailed View:** See full event details, including description, date, location, and real-time remaining spots.
- **Secure Authentication:** Seamless user registration and JWT-based login.
- **Seat Booking:** Authenticated users can book between 1 to 4 seats for any upcoming event.
- **Personal Dashboard:** View and manage all registered events, with the ability to cancel bookings.

### **Admin Functionality**
- **Protected Dashboard:** Role-based access ensures only administrators can access the event management panel.
- **Full CRUD Operations:**
  - **Create:** Add new events through a rich form with image upload capabilities.
  - **Read:** View a comprehensive list of all events and their live registration status.
  - **Update:** Edit any detail of an existing event.
  - **Delete:** Remove events from the platform.
- **System Monitoring:** At-a-glance view of event registrations to monitor performance.

___

# Getting Started & How to Run

To run the full application locally, you will need to set up and run both the backend and the frontend. **The backend server must be running before you start the frontend.**

### Prerequisites
- [Node.js](https://nodejs.org/) (v18.x or later)
- [npm](https://www.npmjs.com/)
- [PostgreSQL](https://www.postgresql.org/) database server installed and running.
- [Git](https://git-scm.com/)

### Step 1: Run the Backend Server

1.  **Clone the Repository:**
    ```bash
    git clone https://github.com/JALAL-00/Event-Buddy-Event-Management-System.git
    cd Event-Buddy-Event-Management-System
    ```

2.  **Navigate to the Backend Directory:**
    ```bash
    cd backend
    ```

3.  **Install Dependencies:**
    ```bash
    npm install
    ```

4.  **Set Up Environment Variables:**
    Create a `.env` file in the `/backend` directory with the following content. **Make sure to update these values to match your local PostgreSQL configuration.**
    ```plaintext
    # backend/.env

    DATABASE_HOST=localhost
    DATABASE_PORT=5432
    DATABASE_USERNAME=postgres
    DATABASE_PASSWORD=your_postgres_password_here
    DATABASE_NAME=eventbuddy

    JWT_SECRET=a8b3c1d9e7f5a2b8d4e6f3a1c9d8b7c6a5b4c3d2e1f0a9b8c7d6e5f4a3b2c1d0
    JWT_EXPIRES_IN=1d
    ```

4.1. **Database Setup:**

1.  Open **pgAdmin 4**.
2.  Connect to your local PostgreSQL server.
3.  **Drop** any existing `eventbuddy` database.
4.  Right-click on `Databases` -> `Create` -> `Database...`.
5.  Enter `eventbuddy` as the Database name and click Save.
6.  The application will automatically create the necessary tables when it first starts (`synchronize: true` is enabled for development).


5.  **Run the Backend:**
    The server will start, connect to the database, and automatically seed the admin user.
    ```bash
    npm run start:dev
    ```
    The backend API will now be running at `http://localhost:3000`.

### Step 2: Run the Frontend Application

1.  **Open a New Terminal** in the root project directory.

2.  **Navigate to the Frontend Directory:**
    ```bash
    cd frontend
    ```

3.  **Install Dependencies:**
    ```bash
    npm install
    ```

4.  **Set Up Environment Variables:**
    Create a `.env.local` file in the `/frontend` directory. **This step is mandatory.**
    ```plaintext
    # frontend/.env.local

    NEXT_PUBLIC_API_BASE_URL=http://localhost:3000
    ```

5.  **Run the Frontend:**
    ```bash
    npm run dev
    ```
    The application will be available at `http://localhost:3001`.

---

## Test Credentials & Usage

To test the different user roles, use the following credentials on the application's login and registration pages.

### Admin Account (Auto-created)
The backend automatically creates an admin user on its first run. Go to the login page (`http://localhost:3001/login`) and use these details to access the admin dashboard.

- **Email:** `admin.jalal@gmail.com`
- **Password:** `AdminJalal123@`

_Note: To change the default admin credentials, edit the variables in `backend/src/seed/seed.service.ts` and reset the database._

### Regular User Account (Manual Registration)
To test as a regular user, you must first register a new account.

---- Here is a demo for regiter & login ----

**1. Enter the following details:**
- **Full Name:** `Jalal Uddin`
- **Email:** `jalaluddin0046@gmail.com`
- **Password:** `ValidPassword123@`

After registering, the application will automatically log you in and redirect you to the user dashboard. You can then log out and log back in using this email and password.

### Regular User Account (Manual Login)

**1. Enter the following details:**
- **Email:** `jalaluddin0046@gmail.com`
- **Password:** `ValidPassword123@`

---

## Technology Stack

This project is a modern full-stack monorepo with a clear separation between the client and server applications.

### 🖥️ Frontend
- **Framework:** **Next.js** (App Router)
- **Language:** **TypeScript**
- **Styling:** **Tailwind CSS**
- **API Communication:** **Axios**
- **State Management:** **React Context API**

### 🗄️ Backend
- **Framework:** **NestJS**
- **Language:** **TypeScript**
- **Database:** **PostgreSQL** with **TypeORM**
- **Authentication:** **JWT** with **Passport.js**
