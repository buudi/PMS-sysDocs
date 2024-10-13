Manage Tenant Lifecycle Scenarios

1. New Tenant Onboarding 
2. Renewal of tenant contract
3. Tenant move-out
	1. move-out at end of contract
	2. move-out before end of contract
4. Tenant move to different unit
## Scenario 1: New Tenant Onboarding 
- caretaker makes a new tenant record.
- caretaker makes a new contract record under the property unit record, with relation to tenant record just created.
- invoice draft is automatically generated based on the contract terms.
## Scenario 2: Renewal of tenant record
- previously in tenant onboarding, caretaker has the option to set the contract as auto renewable, that is if monthly contract, the contract renews automatically every month.
- if not set as auto renewable, caretaker must make a new contracts manually
- invoice draft is automatically generated based on the contract terms.
## Scenario 3: Tenant Move-out
- **Case 1:** one-time (non-renewable) Contracts
	- **Case 1.1:** Move-out at end of contract
		- caretaker archives the tenant record.
	- **Case 2.2**: Move-out before end of contract (reimbursement for remaining days)
		- caretaker makes a "returned rent" record for the remaining days of contract
		- caretaker archives the tenant record
- **Case 2:** Auto-renewable contracts
	- when tenant decides to move-out, caretaker must flag the contract (move-out flag) BEFORE the contract ends.
	- a contract flagged as (move-out) has two options
		- **Option 1:** Move-out at end of contract:
			- contract stops next re-new.
			- caretaker archives the tenant record
		- **Option 2:** Move-out before end of contract
			- contract stops next re-new.
			- caretaker makes a "returned rent" record for the remaining days of contract.
			- caretaker archives the tenant record.

## Scenario 4: Tenant move to different unit
- Caretaker must flag the contract as "move-out".
- The procedures from Scenario 3 is followed except that the tenant record is NOT archived.