
[[#overview]]
[[#Current way of operation]]
[[#Rough Requirements for System Components]]
[[Functional Requirements]]
[[Use cases]]


[[Starter REFINE Template Requirements]]

# overview:
A property management system for a properties firm, mainly focusing on (1) leasing rooms for bachelors but also (2) leases whole apartments and houses.

The firm have been increasing the number of properties they are leasing and so responsibility is becoming harder and harder to manage.


titles:
1. [[Lease of beds for bachelors.]]
2. [[Lease of whole properties.]]
### Current way of operation:
lets start with the leasing of rooms or beds to individual bachelors(1), since it's the largest faction of the firm business model.

there are **caretakers** who are assigned to one or more apartment/house(properties)

the caretakers are responsible for collecting rent, handling new tenants, paying for any expenses. All of these are recorded in a physical notebook. A record of all tenants with information regarding their rent, date of entry and day of rent collection. this is the most important part that has a lot of complexities.

titles:
1. [[Collect rents]]
2. [[handle tenants]]
3. [[record expense]]

collecting of the rent can be either cash or bank, fully or partially, this is all recorded in the notebook

By the end of the month, all the caretakers gather for a meeting, where they transfer all the records in the notebook to a spreadsheet, thus generating a monthly report of revenue, expenses and other information of new tenants or removed tenants are also recorded in the excel sheet to reflect the changes.

The finances are then shared with the partners, each property is shared by partners while some are not.
the report must also include how much gross and net revenue/profit is shared for each partner for what properties.
### Rough Requirements for System Components

#### Users Component
we start with the users roles, there will be an admin (Manager) who creates the properties and assigns caretakers to properties.

Manager Responsibilities:
- Create and manage user accounts (Caretakers).
- Adds partners to properties
- Monitor system activities and generate reports.
Additional Functions:
- Password reset functionality.

Caretaker Responsibilities:
- Collect rent from tenants. (cash/bank)
- Handle new tenant onboarding.
- Record expenses related to the properties.
- Tenant management (e.g., move-in, move-out, lease renewals).

#### Property Component
- manager creates a property, includes basic information (like type of property and no of rooms/beds) and assigns a caretaker.
- a property can either be a (1) whole property (lease whole property) or (2) bachelor property (lease beds or rooms)
- manager assigns partners and set their shares. 

#### Property Management Component
- caretaker records revenue (cash or bank)
- caretaker records expenses (allow for exports and import of json file from expenses mobile apps)
- caretaker create contract for new tenants
- caretaker renews contracts for tenants
