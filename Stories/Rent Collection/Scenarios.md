There are 3 types of users involved
1. Tenant - The person who rents the property.
2. Caretaker - The person responsible for collecting rent and following up with tenants.
3. Manager -The person who ratifies deposit requests submitted by the caretaker at the end of the month to generate financial reports.

**Example:** We have an apartment called "Marina Apartment".
- Tenant Ahmed is required to pay AED 1000 per month according to his contract.
- The rent due date is the first of February.
- The system automatically generates an invoice for AED 1000 to the tenant 3-5 days before the due date (invoice status: "Draft").
- the caretaker can modify the invoice and add any discounts.
- Once the caretaker approves the invoice, it is activated (invoice status updated to "Active")
    - (Optional) And automatically send it to the tenant's email.

## **Scenario 1: Full Rent Payment**
1. Ahmed receives an invoice for AED 1000 due on February 1st.
2. **Case: Bank payment:**
    - Ahmed pays the full amount to the bank and informs the caretaker.
    - The caretaker records the payment in the system (the balance is added to the caretaker's account) stating that AED 1000 has been paid to the bank, and the system automatically generates a receipt under the invoice.
    - The invoice status changes to **"Paid"**.
3. **Case: Cash payment:**
    - The tenant pays cash to the caretaker.
    - The caretaker records the payment in the system (the balance is added to the caretaker's account) stating that AED 1000 has been received, and the system automatically generates a receipt under the invoice.
    - The invoice status changes to **"Paid"**.
4. The caretaker reviews their account, which includes records of cash/bank money received and expense records, and then submits a deposit request to the main account.
5. The manager approves the deposit from the caretaker's account, the caretaker's account is cleared and the records are transferred to the main revenue and expense account.
6. The manager can now generate financial reports that show expected and actual revenue, and include any incomplete payments or discounts that affected revenue matching.

## **Scenario 2: Partial Rent Payment**
1. Ahmed receives an invoice for AED 1000 due on February 1st.
2. **Case: Bank payment:**
    - Ahmed pays part of the amount (e.g. AED 500) to the bank and informs the caretaker of the payment.
    - The caretaker records the payment in the system (the balance is added to the caretaker's account) stating that AED 500 has been paid to the bank, and the system automatically generates a receipt under the invoice.
    - The invoice status changes to **"Outstanding"**.
3. **Case: Cash payment:**
    - Ahmed pays part of the amount (e.g. AED 500) cash to the caretaker.
    - The caretaker records the payment in the system (the balance is added to the caretaker's account) stating that AED 500 has been received, and the system automatically generates a receipt under the invoice.
    - The invoice amount changes to the remaining balance (e.g. AED 500).
    - The invoice status changes to **"Outstanding"**.
4. The caretaker reviews their account, which includes records of cash/bank money received and expense records, and then submits a deposit request to the main account.
5. The manager approves the deposit from the caretaker's account, the caretaker's account is cleared and the records are transferred to the main revenue and expense account.
6. The manager can now generate financial reports that show expected and actual revenue, and include any incomplete payments or discounts that affected revenue matching.

## **Scenario 3: Tenant pays rent late**
Question: What happens if the tenant doesn't pay rent by the due date or if rent is only partially paid?
- invoices have six statuses: "Draft", "Active", "Paid", "Paid Late", "Outstanding", "Overdue".
- In the case where a payment is late, it could be that tenant hasn't paid any amount "Overdue" or have partially paid the invoice "Outstanding". 
- Caretakers will have a constant area in their dashboard to notify them of incomplete and outstanding payments
- In the financial report outstanding balance is listed with incomplete payments
- when invoice payment is completed late, invoice status gets updated to "paid late"
- later next month or whenever the report is generated, completed late payments are listed in the revenue.

## **Scenario 4: Tenant vacates early**
Question: How is rent handled if the tenant leaves the property before the end of the lease?
- Case: AED 1000 invoice is paid and tenant leaves after 15 days and requests reimbursement for the remaining 15 days of the month
	- By default a tenant must not get reimbursement for remaining days, however there should be an option to make a "returned rent" (ايجار مرتجع), where it would be deducted from the revenue.
	- caretaker makes a "returned rent" record, which is a standalone process.
	- In the report "returned rent" is deducted from Revenue when calculating gross revenue.

## Scenario 5: Tenant Requests Change of Settlement Date
- **Case:** The tenant occupies the unit on the 25th of the month. The monthly contract specifies that rent must be paid by the 25th of each month. The tenant wishes to change the payment date to the 1st day of the month instead.
    - In such cases, caretakers are required to draft a special contract for the remaining days from the 25th to the end of the month.
    - Subsequently, a new contract can be initiated on the 1st of the following month.











