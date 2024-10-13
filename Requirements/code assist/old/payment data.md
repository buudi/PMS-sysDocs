```sql
CREATE TABLE payments (
    payment_id SERIAL PRIMARY KEY,
    tenant_id integer references tenants(id) not null , -- Foreign key to reference the user making the payment
    amount NUMERIC(10, 2) NOT NULL,
    payment_method VARCHAR(50) NOT NULL,
    payment_status VARCHAR(20) NOT NULL,
    transaction_id VARCHAR(255), -- Stripe transaction ID or other identifier
    payment_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    notes TEXT,
    stripe_payment_details JSONB -- Store additional Stripe payment details
);
```


```javascript
// contract if there is frequency
 const values  = [
	tenant_id,
	property_id,
	contract.start_date,
	contract.end_date,
	contract.rental_amount,
	contract.rental_frequency,
	contract.rental_frequency_unit,
	contract.rental_payment_method,
];
```



let get things short, I have this system to manage real estate properties, a client service (web application) exists where customers could rent properties for a period of month or more, 
when a customer books and successfully pays for the property, they become tenants.
there is another system lets call it the admin system, where managers and caretakers(employees assigned to take care of tenant requests, they are assigned beforehand) can manage the system (something like an internal tool), now I am developing this admin system, currently I am developing the page where caretakers manage booking and payments of tenants, the process looks like this:

customer books a property (enters their information and length of rent) --> customer pays using stripe --> if payment success the object is sent to the backend (the object will look similar to figure 1 below) --> backend receives the object --> backend stores payment information in payment table  --> backend issues a new contract with the contract information received from the frontend object and stores it in the contracts table --> the backend --> backend generates invoice and sets it to paid and stores it in the invoice table.

figure 1:
```json
{
    "tenant": {
        "email": "ahmedMagdi@example.com",
        "phone_country_code": "+60",
        "phone_number": "1234567890",
        "fname": "Ahmed",
        "lname": "Magdi",
        "ic_no": "111111111",
        "date_settle_in": "2023-12-27"
    },
    "payment": {
        "amount": "3200",
        "payment_method": "stripe",
        "transaction_id": "<stripe transaction id here>",
        "payment_status": "completed",
        "stripe_payment_details": {
            
        } // here the json returned by stripe
    },
    "contract": {
        "property_id": "22",
        "contract_start": "2023-12-27",
        "contract_end": "2024-01-27",
        "rent": "3200"
    }
}
```


now I want to create the admin page for the assigned caretaker to manage these information, I want the caretaker to be able to extend, modify contracts, modify invoices, issue new invoices, manage and so on.

how can I approach this? what will the page look like? what should I consider when making this page? give me some insights on what the user interface look like, perhaps make me a basic wireframe.



```html
<flex column>

	<flex row>
		<PropertyCard>
		<flex column>
			<ContractStatusCard>
			<flex row>
				<card /><card />
				<flex column>
					<card>
					<card>
				</flex
			</flex>
		</flex>
	</flex>
	
	<InvoiceTable>
	
</flex>
```

