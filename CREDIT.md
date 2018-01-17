# Monetary Reporting API

### Credit Reporting Requests
* [Credit Transactions](#credit-transactions)

## Credit Transactions
Retrieve credit transactions for the authenticated mid. `GET` [/v1/Credit/Transactions/{StartDate}/{EndDate}](https://reporting-cert.monetary.co/swagger/ui/index#!/Credit/Credit_Transactions)

### Response JSON
```
[
  {
    "Reference": 8383830000000018,
    "DateTimeLocal": "2018-01-16T16:19:19.36",
    "Transcode": "VoidSale",
    "Status": "Success",
    "CardBrand": "VISA",
    "Last4": 1234,
    "Token": "card********M0N1",
    "Invoice": "ABC123",
    "Amount": 12.11,
    "Mid": "123",
    "Captured": true
  },
  {
    "Reference": 8383830000000026,
    "DateTimeLocal": "2018-01-16T16:19:17.83",
    "Transcode": "Sale",
    "Status": "Approved",
    "CardBrand": "VISA",
    "Last4": 1234,
    "Token": "card********M0N1",
    "Experation": 1901,
    "Invoice": "ABC123",
    "Amount": 12.11,
    "Mid": 123,
    "Captured": true
  }
]
```
<br />
