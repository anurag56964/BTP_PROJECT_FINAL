# BTP405 Project 2

# BTP405 Project 2

## Submission Details:

- Contributor: Anurag Das
- Contact: adas35@myseneca.ca

## Project Overview:

This project focuses on creating a cloud-based system for restaurant reservations that enhances the booking, managing, and cancellation processes online. It is designed to improve the interaction between customers and restaurant staff through functionalities like instant booking confirmations, easy management of customer data, and automated updates regarding reservations.

## Objectives:

- Facilitate an easier table booking process for customers.
- Increase operational efficiency for restaurant staff.
- Boost satisfaction levels among customers.
- Build a system that is scalable, adaptable, and maintainable, utilizing a microservices architecture.

## Specifications:

- A customer-facing interface for booking tables.
- A staff interface for managing reservations and customer details.
- Automatic notifications for booking confirmations and cancellations.
- Secure mechanisms for user authentication and authorization.
- A scalable architecture to accommodate varying demands.

## Intended Audience:

The system is targeted at restaurant owners, managers, and patrons interested in an efficient online reservation system.

## Main Features:

- Management of user accounts.
- Capabilities for booking and canceling reservations.
- Live updates on the availability of tables.
- Secure storage and handling of customer profiles.
- Automatic notifications about reservations.
- Analytical tools for restaurant management.

## Challenges Addressed:

- Reducing manual errors and inefficiencies in booking processes.
- Streamlining the management of reservations and customer data.
- Ensuring customers receive timely information about their bookings.
- Enhancing communication regarding reservations.

## User Narratives:

- Customers should be able to effortlessly set up accounts and book tables.
- Customers should have the ability to filter tables by date, time, and size.
- Staff should have access to real-time updates on table availability.
- Staff should be promptly notified about new bookings or cancellations.
- Customers should receive email confirmations upon booking.

## Use Cases:

- A customer registers on the website and books a table via their email.
- Customers can select specific details for their reservation and immediately view available options.
- Upon booking, the system logs the reservation and emails a confirmation to the customer.
- Customers can modify or cancel their bookings directly through their accounts.
- Staff are alerted about new reservations and can adjust table availability as needed.

## API Interactions:

#### Creating a New User

```http
POST /user
Content-Type: application/json
{
    "Name": "Hennah",
    "Email": "hennah@gmail.com"
}
```

## RESULT:
```
Status: 201 Created
{
    "user_id": 1,
    "name": "Hennah2",
    "email": "hennah2@gmail.com"
}
```
#### Making a New Reservation:
```
POST /reservation
Content-Type: application/json

{
    "user_id": 1,
    "reservation_time": "2024-01-19 21:00:00",
    "guests": 9,
    "status": "Confirmed"
}
```
## RESULT:
```
Status: 201 Created
{
    "message": "Reservation Created Successfully."
}

```

## Viewing Reservations:
```
Status: 200 OK
[
   {
      "reservation_id": 1,
      "user_id": 1,
      "reservation_time": "2024-01-19 21:00:00",
      "guests": 9,
      "status": "Confirmed"
   }
]


```
### Modifying a Reservation:
```
PUT /reservation/{reservation_id}
Content-Type: application/json
[
   {
      "reservation_time": "2024-01-19 21:00:00",
      "guests": 19,
      "status": "Confirmed"
   }
]

```

## RESULT:
```
Status: 201 Created
{
    "message": "Reservation Updated Successfully."
}
```

### Canceling a Reservation:
```
DELETE /reservation/{reservation_id}
Status: 200 OK
{
    "message": "Reservation Deleted Successfully."
}

```
