🚀 **Built a PHP CRUD App using Docker Compose (Beginner DevOps Project)**

Simple project to understand how multi-container apps work using Docker Compose 🐳

👉 Goal:
Build a **PHP frontend + MySQL database** setup to **create and list users**

---

### 🧠 Architecture Overview

* PHP + Apache → Runs the frontend
* MySQL → Stores user data
* Docker network → Enables communication using service name (`db`)

---

### ⚙️ docker-compose.yml (Core Idea)

👉 Defined 2 services:

**1. Database (db)**

* MySQL container
* Root password via environment variable
* Port: `3306`

**2. PHP App (php-app)**

* Connected to DB using:

  ```bash
  MYSQL_DBHOST=db:3306
  ```
* Port mapping:

  ```bash
  8081 → 80
  ```

---

### 🔄 How It Works

1. Run:

   ```bash
   docker compose up -d
   ```

2. Open:

   ```bash
   http://localhost:8081
   ```

3. App connects to DB using:

   ```bash
   db:3306
   ```

👉 No need for IPs — Docker handles service discovery internally 🔥

---

### 📊 Output

✔️ Create users
✔️ View user list
✔️ Perform CRUD operations

---

### 💡 Key Learnings

* Docker Compose simplifies multi-container setup
* Containers communicate using **service names (not IPs)**
* Environment variables help configure apps cleanly
* Port mapping connects container apps to the host

---

### 🎯 Takeaway

> “Docker Compose bridges the gap between running single containers and managing real-world multi-service applications.”
