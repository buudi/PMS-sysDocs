**Main Entities:**
- **Property:** Represents real estate units (e.g., Marina Apartment, Mamzar Villa, etc).
- **Tenant:** Represents individuals residing in the properties.
- **Contract:** Defines the rental agreement for tenant (e.g., rent and length of contract)
- **Invoice:** Represents a rent bill issued to a tenant for a specific period.
- **Transaction:** Records all financial transactions related to rent payments, deposits, and expenses.
- **Account:** Represents different accounting entities (e.g., Caretaker Account, Manager Account, Main Revenue/Expense Account).

**Relationships:**
- **Property can have many Contracts.**
- **Contract belongs to one Property.**
- **Tenant can have many Contracts.**
- **Contract belongs to one Tenant.**
- **Invoice belongs to one Contract.**
- **Contract can have many Invoices.**
- **Transaction belongs to one Invoice.**
- **Invoice can have many Transactions.**
- **Transaction belongs to one Account.**
- **Account can have many Transactions.**

**Additional Entities:**
- **User:** Represents system user (caretaker or manager)
- **Caretaker Property:** Represents properties assigned to caretakers.
- **Session:** represents active system login sessions.



