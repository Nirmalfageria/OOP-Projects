# Zomato Clone - Food Ordering System in C++

A **C++ implementation of a Zomato-like food ordering system**. This project lets you **search for restaurants**, **choose menu items**, **manage your cart**, and **place orders** with different payment methods (Credit Card, UPI, etc.). It demonstrates key **object-oriented programming (OOP)** principles, including the **Factory Pattern, Strategy Pattern, and Singleton Pattern**.

---

## Features

- **Search restaurants** by location  
- **Add menu items** to your cart  
- **Checkout** for immediate or scheduled orders  
- **Pay** using multiple payment options  
- **Receive notifications** about your order status  
- Supports both **Delivery** and **Pickup** orders  
- Simple, **command-line interface** for easy demonstration  

--- 

## How to Run

1. Open `main.cpp` in your preferred C++ IDE  
2. Click **Run** or compile with g++:

```bash
g++ -std=c++17 -I. main.cpp -o main
./main
```

---

## UML Diagram

```
            +----------------+
            |      User      |
            +----------------+
                    |
                    v
            +----------------+
            |      Cart      |<---------------------+
            +----------------+                      |
            | - items        |                      |
            | - restaurant   |                      |
            +----------------+                      |
                    |                               |
                    v                               |
            +----------------+                      |
            |   MenuItem     |                      |
            +----------------+                      |
                                                    |
                                                    v
                  +----------------------+    +--------------------+
                  |      Order           |<---|   RestaurantManager |
                  +----------------------+    +--------------------+
                  | - user               |
                  | - items              |
                  | - totalAmount        |
                  | - status             |
                  +----------------------+
                          ^
        +-----------------+-----------------+
        |                                   |
+------------------+                +------------------+
|  DeliveryOrder   |                |   PickupOrder    |
+------------------+                +------------------+
| - deliveryAddress|                | - pickupAddress  |
+------------------+                +------------------+
        ^
        |
+--------------------+
| OrderFactory        |
+--------------------+
| createOrder()       |
+--------------------+
        ^
+--------------------+     +-----------------------+
| NowOrderFactory     |     | ScheduledOrderFactory |
+--------------------+     +-----------------------+
| createOrder()       |     | createOrder()         |
+--------------------+     +-----------------------+

Order --> PaymentStrategy --> CreditCard / UPI
Order --> NotificationService
```

You can also view the UML diagram in `UML.png`.

For details on the project structure, check the `folderstructure` folder.