# WhatNext Vision Motors 🚗

## Project Overview

**WhatNext Vision Motors** is a Salesforce-based Vehicle and Mobility Management System designed to improve customer experience, simplify vehicle ordering, and streamline automobile business operations.

The system centralizes the management of **customers, vehicles, dealers, vehicle orders, test drives, and service requests** in Salesforce.

The project uses Salesforce CRM features along with **Flows, Apex Triggers, Trigger Handlers, and Batch Apex** to automate important business processes.

## Objectives

* Manage customer and vehicle information in a centralized Salesforce system.
* Maintain vehicle stock and availability.
* Manage dealers and their locations.
* Automate vehicle order processing.
* Automatically assign the nearest dealer to a customer.
* Prevent orders when the selected vehicle is unavailable.
* Automatically update order status based on stock availability.
* Send reminders for scheduled test drives.
* Process large numbers of vehicle orders using Batch Apex.
* Reduce manual work and improve operational efficiency.

## Key Features

### 1. Customer Management

Stores customer details such as:

* Customer Name
* Email
* Phone
* Address
* Preferred Vehicle Type

### 2. Vehicle Management

Maintains:

* Vehicle Name
* Vehicle Model
* Stock Quantity
* Price
* Dealer
* Vehicle Status

Vehicle status can be:

* Available
* Out of Stock
* Discontinued

### 3. Dealer Management

Stores dealer information including:

* Dealer Name
* Dealer Location
* Dealer Code
* Phone
* Email

### 4. Vehicle Order Management

Tracks:

* Customer
* Vehicle
* Order Date
* Order Status

Order status includes:

* Pending
* Confirmed
* Delivered
* Canceled

### 5. Test Drive Management

Manages:

* Customer
* Vehicle
* Test Drive Date
* Test Drive Status

The system can automatically send an email reminder before a scheduled test drive.

### 6. Service Request Management

Tracks:

* Customer
* Vehicle
* Service Date
* Issue Description
* Service Status

## Salesforce Automation

### Record-Triggered Flow – Nearest Dealer Assignment

When a new vehicle order is created:

1. Retrieve the customer information.
2. Identify the customer's location.
3. Find the appropriate/nearest dealer.
4. Update the vehicle order with the selected dealer.

This reduces manual dealer assignment and connects customers with a convenient dealer.

### Record-Triggered Flow – Test Drive Reminder

A Record-Triggered Flow is used to send an automatic email reminder for scheduled test drives.

Process:

1. Trigger when a Test Drive record is created or updated.
2. Check whether the status is **Scheduled**.
3. Create a scheduled path.
4. Retrieve customer information.
5. Send an email reminder before the test drive.
6. Activate the flow.

The project specifies a reminder such as **one day before the test drive**.

## Apex Automation

The project uses Apex to implement business rules and automate vehicle-order processing.

### Apex Trigger

The Apex Trigger is used to check vehicle availability when an order is created and apply the required business rules.

### Trigger Handler

A Trigger Handler is used to keep Apex code organized, reusable, and maintainable.

### Batch Apex

Batch processing is used to:

* Process large numbers of order records.
* Periodically check vehicle stock availability.
* Update order statuses in bulk.
* Set unavailable orders to **Pending**.
* Set available orders to **Confirmed**.

## Custom Objects

The project contains the following major custom objects:

| Object                     | Purpose                              |
| -------------------------- | ------------------------------------ |
| Vehicle__c                 | Stores vehicle information and stock |
| Vehicle_Dealer__c          | Stores dealer information            |
| Vehicle_Order__c           | Manages vehicle orders               |
| Vehicle_Customer__c        | Stores customer information          |
| Vehicle_Test_Drive__c      | Manages test drive appointments      |
| Vehicle_Service_Request__c | Manages vehicle service requests     |

## Technologies Used

* Salesforce CRM
* Lightning App
* Custom Objects
* Custom Fields
* Lookup Relationships
* Salesforce Flow
* Record-Triggered Flow
* Scheduled Paths
* Email Automation
* Apex
* Apex Triggers
* Trigger Handler
* Batch Apex
* Scheduled Jobs

## Project Workflow

```text
Customer
   ↓
Select Vehicle
   ↓
Create Vehicle Order
   ↓
Check Vehicle Availability
   ↓
Assign Nearest Dealer
   ↓
Update Order Status
   ↓
Pending / Confirmed
   ↓
Order Processing
```

For test drives:

```text
Schedule Test Drive
        ↓
Status = Scheduled
        ↓
Scheduled Path
        ↓
Retrieve Customer Details
        ↓
Send Email Reminder
```

## Expected Benefits

* Faster vehicle order processing
* Reduced manual work
* Better vehicle stock management
* Automated dealer assignment
* Improved customer communication
* Reduced order-processing errors
* Centralized customer and vehicle information
* Efficient bulk processing of orders

## Learning Outcomes

Through this project, users learn how to:

* Create and manage Salesforce custom objects and fields.
* Create relationships between objects.
* Build a Lightning App.
* Use Salesforce Flow for business automation.
* Implement Apex Triggers and Trigger Handlers.
* Use Batch Apex for large-volume data processing.
* Automate email notifications.
* Manage vehicle stock and order status.
* Build a centralized mobility-management solution.

## Conclusion

**WhatNext Vision Motors** demonstrates how Salesforce can be used to build an automated mobility-management solution. By combining CRM functionality with Flow, Apex, triggers, and batch processing, the system helps automate vehicle ordering, dealer assignment, stock management, test-drive reminders, and order-status processing.
