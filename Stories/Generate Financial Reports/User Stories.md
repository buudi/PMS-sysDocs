## Scenario: Generate Financial Reports

Actors: **Manager** is the only actor for this Scenario

1. As a manager, I want to be able to create financial reports that include:
    - **Expected Revenue:** This includes the total expected rent amount for all tenants during the reporting period (monthly).
    - **Actual Revenue:** This includes the total rent amount actually collected from tenants during the reporting period (excluding discounts).
    - **Outstanding Payments:** This includes any rent amounts that tenants have not fully paid by the due date.
    - **Rent Discounts:** This includes any discount amounts offered to tenants during the reporting period.
    - **Returned Rent:** This includes any rent amounts returned to tenants who vacate the property before the end of the lease contract.
    - **Net Revenue:** Calculated by adding returned rents to actual revenues and subtracting discounts.
    - **Operating Expenses:** This includes all expenses associated with property management (such as maintenance, repairs, utilities, etc.).
    - **Net Profit:** Calculated by subtracting total expenses from net revenue.

2. As a manager, I want to be able to generate more detailed reports, including:
    - **Income Breakdown:**
        - **Rent by Unit:** Reveals the rent collected for each unit (such as property or bed).
        - **Rent by Tenant:** Reveals the rent collected for each tenant.
        - **Late Rents:** Tracks income resulting from rent payment delays.
    - **Expense Breakdown:**
        - **Itemized Expenses by Category:** Distributes expenses by category (e.g., maintenance, repairs, utilities, etc.).
    - **Key Performance Indicators (KPIs):**
        - **Vacancy Rate:** Tracks the percentage of unoccupied units.
        - **Collection Rate:** Measures the percentage of rent collected on time.
    - **Customization:**
        - Allows customization of reporting periods (e.g., weekly, monthly, quarterly, etc.).
