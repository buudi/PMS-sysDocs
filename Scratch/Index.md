
[[#overview]]
[[#Current way of operation]]
[[#Rough Requirements for System Components]]
[[Functional Requirements]]
[[Use cases]]


# overview:
a property management system for a properties firm, mainly focusing on leasing rooms for bachelors(1) but also leases whole apartments and houses(2).

they have been increasing the number of properties they are leasing and so its becoming harder and harder to manage everything.

titles:
1. [[Lease of beds for bachelors.]]
2. [[Lease of whole properties.]]
### Current way of operation:
lets start with the leasing of rooms or beds to individual bachelors(1), since it's the largest faction of the firm business model.

there are **caretakers** who are assigned to one or more apartment/house (we will call them properties)

the caretakers are responsible for collecting rent, handling new tenants, paying for any expenses. All of these are recorded in a physical notebook. A record of all tenants with information regarding their rent, date of entry and day of rent collection. this is the most important part that has a lot of complexities.

titles:
1. [[Collect rents]]
2. [[handle tenants]]
3. [[record expense]]

collecting of the rent can be either cash or bank, fully or partially, this is all recorded in the notebook

By the end of the month, all the caretakers gather for a meeting, where they transfer all the records in the notebook to a spreadsheet, thus generating a monthly report of revenue, expenses and other information of new tenants or removed tenants are also recorded in the excel sheet to reflect the changes.

The finances are then shared with the partners, each property is shared by partners while some are not.
the report must also include how much gross and net revenue/profit is shared for each partner for what properties.

Make a proper documentation for the following functional requirements
### Rough Requirements for System Components

#### Users Component
we start with the users roles, there will be an admin who creates the properties and assigns caretakers to properties.

Admin Responsibilities:
- Create and manage user accounts (Caretakers).
- Adds partners to properties
- Define access levels and permissions for each user role.
- Monitor system activities and generate reports.
Additional Functions:
- Password reset functionality.
- User activity logs for auditing purposes.

Caretaker Responsibilities:
- Collect rent from tenants.
- Handle new tenant onboarding.
- Record and manage expenses related to the properties.
Additional Functions:
- Tenant management (e.g., move-in, move-out, lease renewals).
- Reporting functionality for rent collection and expenses.
- User activity logs for auditing purposes.

#### Property Component
- admin creates a property, includes basic information (like type of property and no of rooms/beds) and assigns a caretaker.
- a property can either be a (1)whole property(lease whole property) or (2)bachelor property(lease beds or rooms)
- admin assigns partners and set their shares. 

#### Property Management Component
- caretaker records revenue (cash or bank)
- caretaker records expenses (allow for exports and import of json file from expenses mobile apps)
- caretaker create contract for new tenants
- caretaker renews contracts for tenants
- Send automated lease renewal reminders to caretakers and tenants.
