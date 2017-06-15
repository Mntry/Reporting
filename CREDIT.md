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
    "DateTimeLocal": "2017-06-15T17:01:48.4191546+00:00",
    "Transcode": "VoidSale",
    "Status": "Success",
    "CardBrand": "VISA",
    "Last4": 1234,
    "Invoice": "ABC123",
    "Amount": 12.11,
    "Mid": "123",
    "Captured": true
  },
  {
    "Reference": 8383830000000026,
    "DateTimeLocal": "2017-06-15T17:00:48.4191546+00:00",
    "Transcode": "Sale",
    "Status": "Approved",
    "CardBrand": "VISA",
    "Last4": 1234,
    "Experation": 1901,
    "Invoice": "ABC123",
    "Amount": 12.11,
    "Mid": 123,
    "Captured": true
  }
]
```
<br />
