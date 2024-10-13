What I want
- I want to automatically generate invoices based on the contract due_date
- 3 days before the due_date for a particular contract the system generates an invoice (that is an invoice record in the database)
- the system must keep track of all contracts in the database and generate the invoices accordingly at the proper time.

Mock data representing contracts stored in the database 
```javascript
const contracts = [
    { id: 1, tenantId: 1, dueDate: new Date('2024-04-01') },
    { id: 2, tenantId: 2, dueDate: new Date('2024-04-10') },
    { id: 3, tenantId: 3, dueDate: new Date('2024-04-15') }
];
```

Mock function to create invoice records in the database
```javascript
function createInvoice(contractId, amountDue, dueDate) {
    console.log(`Invoice created for contract ${contractId} with amount ${amountDue} due on ${dueDate}`);
}
```

Function to generate invoices based on contract due dates
```javascript
function generateInvoices() {
    const currentDate = new Date();
    // Calculate the date 3 days before the current date
    const invoiceGenerationDate = new Date(currentDate);
    invoiceGenerationDate.setDate(invoiceGenerationDate.getDate() - 3);

    // Filter contracts whose due dates match the invoice generation date
    const contractsToGenerate = contracts.filter(contract => contract.dueDate.getTime() === invoiceGenerationDate.getTime());

    // Generate invoices for each contract
    contractsToGenerate.forEach(contract => {
        // Mock function call to calculate amount due (replace with your own logic)
        const amountDue = calculateAmountDue(contract);
        createInvoice(contract.id, amountDue, contract.dueDate);
    });
}
```