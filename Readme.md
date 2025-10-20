# 🏨 Hotel Management API – Postman Collection

This Postman documentation provides sample API requests and instructions for testing the **Hotel Management API**.  
The API allows management of **rooms**, **guests**, and **bookings** using standard RESTful methods: **GET**, **POST**, and **DELETE**.

---

## 🚀 Base URL

```
http://localhost:3000/api
```

> Replace `localhost:3000` with your actual deployed URL if hosted.

---

## 📦 API Endpoints Overview

| Resource | Method | Endpoint | Description |
|-----------|---------|-----------|--------------|
| Rooms     | GET     | `/rooms` | Retrieve all rooms |
| Rooms     | POST    | `/rooms` | Add a new room |
| Rooms     | DELETE  | `/rooms/:id` | Delete a specific room |
| Guests    | GET     | `/guests` | Retrieve all guests |
| Guests    | POST    | `/guests` | Register a new guest |
| Guests    | DELETE  | `/guests/:id` | Delete a guest record |
| Bookings  | GET     | `/bookings` | View all bookings |
| Bookings  | POST    | `/bookings` | Create a new booking |
| Bookings  | DELETE  | `/bookings/:id` | Cancel a booking |

---

## 🧩 Sample Requests

### 1. GET – Retrieve All Rooms
**Endpoint:**  
```
GET /rooms
```

**Description:**  
Fetches all rooms available in the hotel, including occupancy status and price.

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

### 2. POST – Add a New Room
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

### 3. DELETE – Remove a Room
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

## 💡 Notes for Postman Testing

1. **Set Environment Variables**
   - Create a variable in Postman named `base_url` with the value `http://localhost:5000/api`.
   - Use `{{base_url}}/rooms` in your requests for easier environment switching.

2. **Headers**
   - For `POST` and `DELETE` requests, include:
     ```
     Content-Type: application/json
     ```

3. **Authorization (Optional)**
   - If your API uses authentication, include your token in:
     ```
     Authorization: Bearer <your_token_here>
     ```

4. **Error Responses**
   - Invalid requests return structured error messages such as:
     ```json
     {
       "error": "Room not found"
     }
     ```

---

## 📘 Example Postman Folder Structure

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

## 🧾 Version
**API Version:** 1.0.0  
**Last Updated:** October 20, 2025  

---

## 👨‍💻 Developer
**Author:** Jenzel G. Zuniga
**Tech Stack:** Node.js | Express | MongoDB | Postman  
