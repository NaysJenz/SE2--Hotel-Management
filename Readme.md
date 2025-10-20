# 🏨 Hotel Management API – Postman Documentation

**Prepared by:** *Jenzel G. Zuñiga*
**Course & Block:** *Bachelor of Science in Computer Science*

---

## 📖 Overview

This Postman documentation contains sample API requests and guidelines for testing the **Hotel Management API**.
The API enables hotel administrators to manage **rooms**, **guests**, and **bookings** through standard RESTful methods such as **GET**, **POST**, and **DELETE**.

---

## 🌐 Base URL

```
http://localhost:3000/api
```

> Replace `localhost:3000` with your actual server or deployed URL when the API is hosted online.

---

## 📦 API Endpoints

| Resource     | Method | Endpoint        | Description                |
| ------------ | ------ | --------------- | -------------------------- |
| **Rooms**    | GET    | `/rooms`        | Retrieve all rooms         |
|              | POST   | `/rooms`        | Add a new room             |
|              | DELETE | `/rooms/:id`    | Delete a specific room     |
| **Guests**   | GET    | `/guests`       | Retrieve all guest records |
|              | POST   | `/guests`       | Register a new guest       |
|              | DELETE | `/guests/:id`   | Delete a guest record      |
| **Bookings** | GET    | `/bookings`     | View all bookings          |
|              | POST   | `/bookings`     | Create a new booking       |
|              | DELETE | `/bookings/:id` | Cancel a booking           |

---

## 🧩 Sample API Requests

### 1. **GET – Retrieve All Rooms**

**Endpoint:**

```
GET /rooms
```

**Description:**
Fetches all available rooms along with their status and price details.

**Response Example:**

```json
[
  {
    "_id": "670f12345abc",
    "roomNumber": 101,
    "type": "Deluxe Suite",
    "status": "Available",
    "price": 4500
  },
  {
    "_id": "670f67890def",
    "roomNumber": 102,
    "type": "Standard Room",
    "status": "Occupied",
    "price": 2500
  }
]
```

---

### 2. **POST – Add a New Room**

**Endpoint:**

```
POST /rooms
```

**Request Body:**

```json
{
  "roomNumber": 105,
  "type": "Executive Room",
  "status": "Available",
  "price": 4000
}
```

**Response Example:**

```json
{
  "message": "Room added successfully",
  "room": {
    "_id": "67100123abc",
    "roomNumber": 105,
    "type": "Executive Room",
    "status": "Available",
    "price": 4000
  }
}
```

---

### 3. **DELETE – Remove a Room**

**Endpoint:**

```
DELETE /rooms/:id
```

**Example Request:**

```
DELETE /rooms/67100123abc
```

**Response Example:**

```json
{
  "message": "Room deleted successfully."
}
```

---

## 🧠 Notes for Postman Testing

1. **Set Environment Variables**

   * Create a variable named `base_url` in Postman.
   * Example:

     ```
     base_url = http://localhost:5000/api
     ```
   * Then use `{{base_url}}/rooms` in your requests for easier switching between environments.

2. **Headers**

   * For **POST** and **DELETE** requests, always include:

     ```
     Content-Type: application/json
     ```

3. **Authorization (Optional)**

   * If the API requires authentication, include your token:

     ```
     Authorization: Bearer <your_token_here>
     ```

4. **Error Responses**

   * Invalid requests return structured error messages like:

     ```json
     {
       "error": "Room not found"
     }
     ```

---

## 📁 Example Postman Folder Structure

```
Hotel Management API/
├── Rooms/
│   ├── GET All Rooms
│   ├── POST Add Room
│   └── DELETE Room by ID
├── Guests/
│   ├── GET All Guests
│   ├── POST Add Guest
│   └── DELETE Guest by ID
└── Bookings/
    ├── GET All Bookings
    ├── POST Add Booking
    └── DELETE Booking by ID
```

---

## 🧾 Version Info

* **API Version:** 1.0.0
* **Last Updated:** October 20, 2025

---

## 👨‍💻 Developer Information

**Author:** *Jenzel G. Zuñiga*
**Program:** *Bachelor of Science in Computer Science*
**Tech Stack:** *Node.js | Express | MongoDB | Postman*

---

