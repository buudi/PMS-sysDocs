
two entities to consider here
1. Accounts
2. Transactions

attributes:
- Accounts
	1. pk: id                       not null
	2. fk: user `references users(id)`, optional because main revenue and expenses do not reference any user
	3. account_name        not null
	4. balance                   not null
	5. opening_date         optional, bcs main does not need to have an opening date
	6. closing_date           optional
- Transactions
	1. pk: id                               not null
	2. date                                not null
	3. type                                not null  "rent", "expense" or "deposit"
	4. amount                           not null
	5. fk: account                      not null `references accounts(id)`
	6. fk: invoice                       optional unless type = "rent" `references invoice(id)`
	7. notes                              optional
	8. is_deposited                   optional unless type = "rent" or type = "expense"
	10. fk: deposit_transaction_id  `references transactions(id)`and reference type should be "deposit",  optional unless type = "rent" or type = "expense".

rationale behind deposit_transaction_id: lets say we have a certain expense, if is_deposited is true, then it must be part of a deposit record, deposit_transaction_id has the id of that record

![[Pasted image 20240221020220.png]]

implementing the special constraints in transactions table:
1. invoice foreign key is NOT NULL only when type = "rent", for any other type it is optional
2. the flag is_deposited is NOT NULL only when type="rent" or type="expense"
3. deposit_transaction_id references to the same table but the record must be of type="deposit"

In PostgreSQL:
1. **Invoice Foreign Key:** invoice foreign key is NOT NULL only when type = "rent", for any other type it is optional
```sql
ALTER TABLE transactions
ADD CONSTRAINT fk_invoice_required_for_rent 
CHECK (type = 'rent' OR invoice IS NOT NULL);
```

2. **is_deposited Flag:** the flag is NOT NULL only when type="rent" or type="expense"
```sql
ALTER TABLE transactions

ADD CONSTRAINT is_deposited_check 
CHECK (type IN ('rent', 'expense') OR is_deposited IS NOT NULL);
```

3. **deposit_transaction_id Reference:** references to the same table but the record must be of type="deposit"
```sql
ALTER TABLE transactions

ADD CONSTRAINT fk_deposit_transaction_type 
CHECK (type = 'deposit' OR deposit_transaction_id IS NULL);

ADD CONSTRAINT fk_deposit_transaction_refers_to_deposit
CHECK ((deposit_transaction_id IS NULL) 
	   OR 
	   (deposit_transaction_id REFERENCES transactions(id)) 
	   AND
	    (type = 'deposit'));
```
- `fk_deposit_transaction_type`: this constraint ensures that whenever `deposit_transaction_id` is not `NULL`, the `type` must be `'deposit'`.
	1. The `type` column must be `'deposit'`.
	2. If `type` is not `'deposit'`, then `deposit_transaction_id` must be `NULL`.
- `fk_deposit_transaction_refers_to_deposit`: this constraint checks two conditions:
	- Either `deposit_transaction_id` is `NULL`.
	- Or, if `deposit_transaction_id` is not `NULL`, then it must reference a valid `id` in the `transaction` table, and the `type` column must be `'deposit'`.


## Issues with the current transaction table
![[Pasted image 20240221171939.png]]
above is sample data for transactions entity:
- as you see there exist a lot of null values that's because there are many types of transactions but only one entity to facilitate, 
- method represents the rent payment method, only valid when type = "rent", same thing with invoice, so naturally "expense" and 'deposit' and potentially "returned_rent" will all be null
- the solution is to identify which columns relate to what type and make separate tables for each type.
- example notes is relevant to all types of transactions, so we will keep them in the transactions entity
- method and invoice is relevant only for "rent" transactions, so we make a separate table for rent : "rent_records" and have a foreign key in transactions table
- we also implement an expenses and returned rent entities : "expense_records", "returned_rent_records".
- is_deposited, deposit_transaction_id is only relevant to "rent", "expense" and "returned_rent" so we will put them in each type entity.