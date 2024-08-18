# Car-Rental-Management

## Overview

The "Rent a Car" project is a comprehensive system designed to manage car rental services. It allows customers to reserve and rent cars based on their preferences and facilitates the management of car inventory, reservations, and customer information

## Business Requirements

The system determines car rental rates based on the class of the car, offering both daily and weekly rates. Each car is uniquely identified by a Vehicle Identification Number (VIN). Customers can make reservations via phone prior to arriving at the branch. The rental process involves verifying reservations, drawing up rental agreements, and processing payments exclusively via credit card.

## Entity-Relationship Diagram

The system's data management relies on a robust ER model to ensure efficient handling of rental transactions. This diagram provides a visual representation of the relationships between different entities such as cars, customers, reservations, and locations.

## Application Program Design

The application interface includes:

- **Main Page**: Initial landing page for users.
- **Sign Up Page**: Registration for new users.
- **Login Page**: Access for registered users.
- **Car Search Page**: Interface for searching available cars.
- **Booking Confirmation**: Display of booked cars and confirmation details.

## Database Design

The project uses a normalized database schema in 3NF to eliminate redundancy and ensure data integrity. Key tables include:

- **CARS**: Stores car details with VIN as the primary key.
- **CLASS**: Contains rental rate information based on car class.
- **CUSTOMERS**: Holds customer details with CUST_ID as the primary key.
- **LOCATIONS**: Records branch location details.
- **MODEL**: Details of car models, linked to the cars via VIN.
- **RESERVATIONS**: Manages reservation data and is linked to customers and cars.

### Sample SQL Queries

1. **GROUP BY Query**:
   ```sql
   SELECT LOC_ID, COUNT(LOC_ID) 
   FROM LOCATIONS_PHONE 
   GROUP BY LOC_ID;
   ```

2. **GROUP BY with HAVING Query**:
   ```sql
   SELECT CLASS_NAME, COUNT(CLASS_ID) AS COUNT 
   FROM CLASS 
   GROUP BY CLASS_NAME 
   HAVING COUNT(CLASS_ID) > 0;
   ```

3. **Nested Query with IN**:
   ```sql
   SELECT * FROM reservations 
   WHERE CUSTOMER_ID IN (SELECT CUST_ID FROM customers WHERE CUST_ID > 1003);
   ```

4. **Nested Query with ALL**:
   ```sql
   SELECT * FROM reservations 
   WHERE CUSTOMER_ID > ALL (SELECT CUST_ID FROM customers WHERE CUST_ID < 1003);
   ```

## Conclusion

### Group Experience

- **Challenges**: The most challenging aspects were establishing database connections and correctly implementing foreign and primary keys.
- **Achievements**: Designing the database schema was straightforward and facilitated the overall development process.
- **Learnings**: The project enhanced our understanding of database integration with web applications and improved our skills in SQL queries, especially with complex joins and conditions.

### Future Enhancements

In future iterations, we plan to incorporate an admin page and add images of the cars to enhance user interaction and administrative control.
