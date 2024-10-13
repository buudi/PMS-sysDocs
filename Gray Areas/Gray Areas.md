1. what happens to the reports if manager adds single units to a property?
	- how should the system behave when the number of single units modified?
	- I think we should not allow the manager to reduce the number of single units, but we should allow to increase 
	- a special operation to reduce the number of single units can be made, instead of directly affecting the number of single units in database, it first checks the number of active contracts, only if there are vacancy it will allow to reduce the number of single units as long as it doesn't exceed the vacancy rate.


to test:
1. make sure the system doesn't show the non-vacant properties when onboarding a new tenant
2. check that Arabic keyboard (numbers) on mobile is providing correct entry to database


## Brainstorm & Design Transactions and Rent Collection Component logic and interface





#### Interfaces to be designed:
Properties:
- as a user I want to access a property page which includes a statistics summary (like how much revenue, vacant units, etc..)
- as a user I want to be able to record expenses under each property (from the property page)

Tenant :
- as a user I want to access a tenant page, look at tenant summary, and some statistics (next contract renew date, total contracts, revenue, total unpaid invoices, etc.) view his contracts.
- as a user I want to access tenant contract, be able to record an invoice under him.
- as a user I want to be able to flag a contract as move-out and make a returned rent record in the contracts page.
- as a user I want to be able to enter rent payment records under the invoice.
- 


**1. Properties**

- **Properties List:** This page displays a list of all properties under management. Each entry should include a summary like property name, address, unit count, current vacancy, and recent revenue.
- **Property Details:** Clicking on a property from the list opens a dedicated page showcasing details like pictures, unit types, amenities, current tenant list, and financial performance (revenue, expenses, net income, vacant units, outstanding rent owed).
- **Record Expenses:** Within the property details page, a section allows recording expenses related to the property. Users can specify amount, category, date, payee, and upload receipts.
	

Contract Page:
![[Pasted image 20240306153857.png]]

Tenant Page:
![[Pasted image 20240306153917.png]]

Discount Page:
![[Pasted image 20240306153954.png]]

- Move-out page:
![[Pasted image 20240306154024.png]]

Record a rent payment:
![[Pasted image 20240306154100.png]]




Insights (dashboard):
![[Pasted image 20240306154342.png]]

creating custom reports:
![[Pasted image 20240306154357.png]]

making a deposit:
![[Pasted image 20240306154525.png]]
