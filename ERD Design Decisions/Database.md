core entities:
1. users
2. properties
3. tenants
4. contracts
5. accounts
6. invoices
7. transactions

dependent entities:
1. sessions
2. caretaker_properties
3. deposit_records
4. rent_records
5. returned_rent_records
6. expense_records

| **No.** | **Entity**            | **Sub-Entites**               | **Dependence**                            | done? |
| ------- | --------------------- | ----------------------------- | ----------------------------------------- | ----- |
| 1       | users                 | user_roles                    |                                           | yes   |
| 2       | properties            | property_types                |                                           | yes   |
| 3       | tenants               |                               | users                                     | yes   |
| 4       | contracts             |                               | tenants, properties                       | yes   |
| 5       | accounts              |                               | users                                     | yes   |
| 6       | invoices              | invoice_items, invoice_status | users, contracts, tenants                 | yes   |
| 7       | transactions          | transaction_types             |                                           | yes   |
| 8       | sessions              |                               | users                                     | yes   |
| 9       | caretaker_properties  |                               | users, properties                         | yes   |
| 10      | deposit_records       | deposit_status                | transactions                              | yes   |
| 11      | rent_records          | payment_methods               | transactions, invoices, deposit_records   | yes   |
| 12      | returned_rent_records |                               | transactions, contracts, deposit_records  | yes   |
| 13      | expense_records       | expense_categories            | transactions, properties, deposit_records | yes   |
| 14      | *user_roles*          |                               |                                           | yes   |
| 15      | *property_types*      |                               |                                           | yes   |
| 16      | *invoice_items*       |                               |                                           | yes   |
| 17      | *invoice_status*      |                               |                                           | yes   |
| 18      | *transaction_types*   |                               |                                           | yes   |
| 19      | *deposit_status*      |                               |                                           | yes   |
| 20      | *payment_methods*     |                               |                                           | yes   |
| 21      | *expense_categories*  |                               |                                           | yes   |

