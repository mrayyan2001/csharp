# Scope Analysis

## Super Admin

### Login:

- **Method:** Super Admin can log in using either a unique phone number or email along with a password. The password should meet the following requirements:
  - At least 8 characters
  - Contains at least 1 letter, 1 symbol, and 1 digit
- After successful login, an OTP (One-Time Password) will be sent to the client with a 6-digit length for additional security.

### Operations Available to Super Admin (Based on Priority):

1. **CRUD Operations**: Create, Read, Update, and Delete operations are available for all entities.
2. **Import from Excel**: Ability to import data from Excel files.
3. **Export to Excel**: Export data to Excel format.
4. **Aggregation Operations**: Aggregate data for analysis and reporting.
5. **Charts**: Generate charts based on the available data.

### Login Techniques:

1. **Image Password**: Use an image-based password for extra security.
2. **Captcha**: Implement CAPTCHA to verify the user.
3. **Master Password**: A master password can be used for high-level access.
4. **OTP/Two-Factor Authentication**: An OTP will be sent to the client's device to verify identity.
5. **Social Media Login**: Login via social media accounts for convenience.

### Permission Management:

- Each operation in the system has a specific permission associated with it.
- **Explore Permissions**: Super Admin can list all available permissions in the system, displaying attributes like ID, name, and description.
- Super Admin can:
  - Get all permissions
  - Get permissions by ID

### Role Management:

1. **Create New Role**: Define a new role by providing the following details:
   - Name
   - Name in Arabic
   - Description in Arabic
   - List of permissions for the role
2. **Update Existing Role**: Modify the details or permissions of an existing role.
3. **List All Roles**: View all roles in the system.
4. **Manage Role Activation**: Deactivate (soft-delete) a role when necessary.

---

## Office Management (Admin / Office Manager)

### Register a New Office:

The process involves creating an office along with its admin. The required details include:

- **Office Details**:

  - Title in English and Arabic (required)
  - Bio in Arabic and English (required)
  - Image/Logo
  - List of Locations
  - Contact Information (phone, social media links, etc.)
  - Working Hours (start time, end time)
  - Establishment Date
  - Documents related to the office

- **Admin Details**:
  - Admin's Name
  - Admin's Email
  - Admin's Phone
  - Admin's Password

Each location should contain:

- Branch Name
- Country, City, Area/Region, Latitude, Longitude

Contact information should include:

- Phone numbers, social media links (WhatsApp, Instagram, Facebook, Email)

### Office Join Requests:

- **List New Office Requests**: View new office join requests that include logo, name, admin phone, email, and admin details.
- **Approve/Reject Office Requests**: Approve or reject new office requests. Upon rejection, a response email will be sent to the requester.

### Office Management Features:

- **List All Current Offices**: View a list of all active offices with logos, names, branches, cars, contracts, revenue, status, and ratings.
- **Get Office Details**: View detailed information about a particular office.
- **Manage Office Activation**: Activate or deactivate an office as needed.
- **Send Alerts**: Send alerts to office admins.
- **Reset Password**: Send a password reset link to the office admin for added security.
- **Manage Countries, Cities, and Regions**: Modify the country, city, and region for the office.
- **Export Reports**: Export office data to an Excel file.
- **Import/Export Excel**: Manage office-related data through Excel.
- **Aggregation**: Perform data aggregation for analytics and reporting.
- **Generate Charts**: Create charts for visualizing office data.

---

## Car Management (Admin / Office Manager)

### Manage Cars:

1. **List All Available Cars**: View cars by attributes such as brand, model, year, price, main image, and status.
2. **Get Car Details**: View detailed information about a specific car, including fuel type, engine capacity, seats, plate number, color, gear type, and additional images (at least one image is required).
3. **Create a New Car**: Add a new car to the system with documentation images.
4. **Update Car Details**: Modify existing car information.
5. **Manage Car Activation**: Activate or deactivate a car as needed.

---

## Employee Management (Admin / Office Manager)

### Manage Employees:

1. **List Employees**: View a list of employees by ID, name, phone, email, and role.
2. **View Employee Details**: See detailed information about an employee, including branch, profile image, and nationality.
3. **Create Employee**: Add a new employee to the system.
4. **Update Employee Information**: Modify existing employee details.
5. **Manage Employee Activation**: Activate or deactivate an employee as necessary.

---

## Rental Request Management (Admin / Office Manager)

### Manage Rental Requests:

1. **Get All Current Requests**: View all current rental requests by ID, username, phone, days, and car details.
2. **Get Request Details**: View the full details of a rental request, including identity image, driving license image, payment method, delivery type, location, reservation dates, status, and payment status.
3. **Approve/Reject Request**: Approve or reject rental requests based on business rules.

---

## Reservation Management (Admin / Office Manager)

### Manage Reservations:

1. **View Reservations**: See details of reservations by ID, username, phone, days, car, and release date.
2. **Get Reservation Details**: View full details of a reservation.
3. **Update Reservation**: Modify existing reservation details.
4. **Send Alerts**: Notify users of any updates or changes.
5. **Close Reservation**: Close reservations once completed.
6. **Rate Users**: Rate users based on their experience.
7. **Create Car Report**: Generate a report for the returned car.

---

## Client (Customer)

### Client Features:

1. **Signup**: Create a new client account.
2. **Login**: Log in to the system using phone/email and password, followed by OTP verification.
3. **Reset Password**: Reset the client's password if forgotten.
4. **Explore Offices**: View all available offices, search by criteria, or get office details by ID.
5. **Explore Cars**: View available cars, search by criteria, or get car details by ID.
6. **Send Request**: Send rental requests for cars.
7. **Make Payment**: Complete payment for rentals.
8. **View Old Requests**: Access previously submitted requests.
9. **View Current Requests**: View ongoing rental requests.
10. **View Current Reservations**: See active reservations.
11. **View Old Reservations**: Access previous reservations.
12. **View Payments**: View payment history.
13. **Print Invoices**: Print invoices for rentals and services.
14. **Rate Services**: Rate cars, services, or other system features.
15. **Report Problems**: Report issues with services or the system.

---
