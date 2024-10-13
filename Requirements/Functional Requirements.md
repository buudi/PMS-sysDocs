# Al-Jazeera Al-Arabiya Property Management System - System Design Documentation (SDD)


---
## 1. Introduction <a name="introduction"></a>
This document provides a detailed overview of the functional requirements for the Property Management System. The system aims to streamline property leasing operations, including the management of properties, users, and financial transactions.

There are two types of users in the system:
1. Manager (المدير)
2. Caretaker (القائم بالرعاية)

---
## 2. Users Component <a name="users-component"></a>

### Manager Responsibilities <a name="manager-responsibilities"></a>
- Create and manage user accounts for Caretakers.
- Add partners to properties and define their respective shares.
- Define access levels and permissions for each user role.
- Monitor system activities and generate reports.
#### Additional Functions <a name="additional-functions"></a>
- Implement password reset functionality for user accounts. // non primary
- Maintain user activity logs for auditing purposes. // non primary

#### Caretaker Responsibilities <a name="caretaker-responsibilities"></a>
- Collect rent from tenants. (Cash/Bank)
- Handle onboarding of new tenants.
- Record and manage expenses related to the properties.
#### Additional Functions for Caretaker <a name="additional-functions-caretaker"></a>
- Manage tenant lifecycle, including move-ins, move-outs, and lease renewals.
- Generate reports on rent collection and expenses. // non primary

---
### 3. Property Component <a name="property-component"></a>
- Manager creates a property, providing basic information such as type (whole property or bachelor property) and the number of rooms/beds.
- Assign a Caretaker to each property.
- Manager assigns partners to properties and sets their respective ownership shares.

---
### 4. Property Management Component <a name="property-management-component"></a>

#### Recording Revenue and Expenses <a name="recording-revenue-and-expenses"></a>
- Caretaker records revenue from tenants, including both cash and bank transactions.
- Caretaker records property-related expenses, with support for importing/exporting JSON files from expenses mobile apps.

#### Contract Management <a name="contract-management"></a>
- Caretaker creates contracts for new tenants, specifying terms and conditions.
- Caretaker manages lease renewals, ensuring timely updates and compliance with agreements.

#### Lease Renewal Reminders <a name="lease-renewal-reminders"></a>
- Implement automated notifications to remind both Caretakers and tenants about upcoming lease renewals.
- Ensure timely communication and contract updates.

---
This documentation serves as a comprehensive guide to the functional requirements of the Al-jazeera Al-Arabiya Property Management System. It outlines the responsibilities and additional functions of users, property management, and financial transactions within the system. Implementing these features will enhance the efficiency and effectiveness of property leasing operations.