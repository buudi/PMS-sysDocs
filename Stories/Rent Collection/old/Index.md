[[PMS/Stories/Rent Collection/old/Index_ar]]


there are 3 types of users involved
1. Tenant
2. Caretaker - who is responsible for collecting rent 
3. Manager - who ratifies all records of rent collection by the end of the month in order to proceed to financial report generation.

lets say we have an apartment called Marina Apartment
- a tenant called Ahmed has to pay AED1000 every month according to his contract.
- his due date is 1st of February
- 2 days before due date on 30th January the system generates an invoice amounting to AED1000
- the caretaker can modify the invoice and add any discounts.
- caretaker approves the invoice, system automatically sends it to tenant email with due date of 1st February
Now there are 4 possible scenarios for payment:
1. Incomplete bank payment
2. Incomplete cash payment
3. Complete bank payment
4. Complete cash payment

Starting with incomplete bank payment:
1. tenant receives AED 1000 invoice to be paid by 1st of February
2. tenant pays AED 500 to the bank and notifies the caretaker of the payment.
3. caretaker confirms payment, makes a receipt record in the system under the invoice that AED 500 has been paid
4. invoice gets updated, from AED1000 to AED 500
5. invoice status is updated to "partially paid"
6. Manager ratifies payment record, report generated, it showcases the expected revenue, actual revenue then it lists the incomplete payments and discounts that caused the revenue not to match the actual revenue.

Second is incomplete cash payment:
1. tenant receives AED 1000 invoice to be paid by 1st of February.
2. tenant pays the caretaker AED 500 by cash.
3. caretaker records the payment in the system (to the caretaker account), that he received AED 500 and generates a receipt record under the invoice.
4. invoice gets updated, from AED1000 to AED 500.
5. invoice status is updated to "partially paid".
6. Caretakers reviews his account, which includes the records of cash he received and expense records he paid and makes ratification request
7. Manager ratifies caretaker account, caretaker account is now reset and records transferred to the main revenue and expenses account.
8. manager can now generate financial reports, it showcases the expected revenue, actual revenue then it lists the incomplete payments and discounts that caused the revenue not to match the actual revenue.

Third is complete bank payment:
1. tenant receives AED 1000 invoice to be paid by 1st of February.
2. tenant pays AED 1000 to bank and notifies the caretaker
3. caretaker confirms payment, makes a receipt record under the invoice is generated in the system that AED 1000 has been paid
4. Invoice status gets updated to "paid"
5. Manager ratifies payment record, report generated, it showcases the expected revenue, actual revenue then it lists the incomplete payments and discounts that caused the revenue not to match the actual revenue.

Lastly is complete cash payment
1. tenant receives AED 1000 invoice to be paid by 1st of February.
2. tenant pays the caretaker AED 1000 by cash.
3. caretaker records the payment in the system (to the caretaker account), that he received AED 1000, a receipt record under the invoice is made.
4. Invoice status gets updated to "paid"
5. Caretakers reviews his account, which includes the records of cash he received and expense records he paid and makes ratification request
6. Manager ratifies caretaker account, caretaker account is now reset and records transferred to the main revenue and expenses account.
7. Manager can now generate financial reports, it showcases the expected revenue, actual revenue then it lists the incomplete payments and discounts that caused the revenue not to match the actual revenue.








