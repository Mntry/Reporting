
# Monetary Reporting API

### Stored Value Reporting Requests
* [Account Transactions](#account-transactions)
* [Business Liability Current](#business-liability-current)
* [Business Liability Effective](#business-liability-effective)
* [Business Reconcile](#business-reconcile)
* [Business Transactions](#business-transactions)
* [Groups Liability Current](#groups-liability-current)
* [Groups Liability Effective](#groups-liability-effective)
* [Groups Reconcile](#groups-reconcile)
* [Groups Transactions](#groups-transactions)

## Account Transactions
All transactions for a single stored value account<br />

`GET` [/v1/storedvalue/**{Id}**/transactions](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Gift_Account_Transactions)

### Request Fields (**bold** fields required)
| Field                         | Type    | Description              | Location |
|-------------------------------|---------|--------------------------|----------|
| **Id**                        | number  | SV Account Number        | URL      |

### Response JSON
```
[
  {
    "Reference": 102394,
    "DateTimeLocal": "2017-06-05T14:59:40.3699059+00:00",
    "Trancode": "Sale",
    "Status": "Approved",
    "Message": "no real message",
    "Account": "8383830000000018",
    "invoice": "T3HB1LLS",
    "Amount": 123.45,
    "IsBulk": true,
    "IsPromo": false,
    "VoidID": 5225
  }
]
```

## Business Liability Current
Current liability on business owned accounts<br />

`GET` [/v1/storedvalue/liabilityCurrent](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Single_Location_Gift_Current_Liability)

### Response JSON
```
[  
   {  
      "Account":"8383830000000034",
      "Balance":"225.00"
   },
   {  
      "Account":"8383830000000042",
      "Balance":"113.00"
   }
]
```
<br />

## Business Liability Effective
Liability as of effective date on business owned accounts<br />

`GET`  [/v1/storedvalue/liabilityEffective?EffectiveDate=**{EffectiveDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Single_Location_Gift_Effective_Liability)

### Request Fields (**bold** fields required)
| Field                          | Type    | Description              | Location |
|--------------------------------|---------|--------------------------|----------|
| **EffectiveDate** <sup>1</sup> | Date    | Liability as of beginning of this day. | URL      |

<sup>1</sup> Date format is yyyy-MM-dd.<br />

### Response JSON
```
[  
   {  
      "Account":"8383830000000034",
      "Balance":"25.00"
   },
   {  
      "Account":"8383830000000042",
      "Balance":"113.00"
   }
]
```
<br />

## Business Reconcile
Net change in liability for the date range partitioned by group<br />

`GET` [/v1/storedvalue/reconcile?StartDate=**{StartDate}**&EndDate=**{EndDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Single_Location_Gift_Reconciliation)

### Request Fields (**bold** fields required)
| Field                         | Type    | Description              | Location |
|-------------------------------|---------|--------------------------|----------|
| **StartDate** <sup>1</sup>    | Date    | Start date               | URL      |
| **EndDate** <sup>1</sup>      | Date    | End date                 | URL      |

<sup>1</sup> Date format is yyyy-MM-dd.<br />

### Response JSON
```
[  
   {  
      "GroupId":1,
      "Group":"Bark & Meow",
      "Amount":"-11.23"
   }
]
```
<br />

## Business Transactions
Transactions in the date range<br />

`GET` [/v1/storedvalue/transactions?StartDate=**{StartDate}**&EndDate=**{EndDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Single_Location_Gift_Transactions)

### Request Fields (**bold** fields required)
| Field                         | Type    | Description              | Location |
|-------------------------------|---------|--------------------------|----------|
| **StartDate** <sup>1</sup>    | Date    | Start date               | URL      |
| **EndDate** <sup>1</sup>      | Date    | End date                 | URL      |

<sup>1</sup> Date format is yyyy-MM-dd.<br />

### Response JSON
```
[
   {
      "Reference": 102394,
      "DatetimeLocal": "2018-01-30T03:58:20.93",
      "Trancode": "Sale",
      "Status": "Approved",
      "Message": null,
      "Invoice": "T3HB1LLS",
      "Account": "8383830000000018",
      "Amount": -5.95,
      "IsBulk": false,
      "IsPromo": false,
      "VoidId": null
   },
   {
      "Reference": null,
      "DatetimeLocal": "2018-01-30T03:58:20.93",
      "Trancode": "Set",
      "Status": "Error",
      "Message": "Invalid Account/CVV/Identifier",
      "Invoice": null,
      "Account": "8282820000001894",
      "Amount": null,
      "IsBulk": false,
      "IsPromo": false,
      "VoidId": null
   }
]
```
<br />

## Groups Liability Current
Current liability on group owned accounts<br />

`GET` [/v1/storedvalue/groups/**{id}**/liabilityCurrent](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Group_Gift_Current_Liability)

### Request Fields (**bold** fields required)
| Field                          | Type    | Description              | Location |
|--------------------------------|---------|--------------------------|----------|
| **Id**                         | Integer | Group Id.                | URL      |


### Response JSON
```
[  
   {  
      "Account":"8383830000000034",
      "Balance":"225.00"
   },
   {  
      "Account":"8383830000000042",
      "Balance":"113.00"
   }
]
```
<br />

## Groups Liability Effective
Liability as of effective date on group owned accounts<br />

`GET` [/v1/storedvalue/groups/**{Id}**/liabilityEffective?EffectiveDate=**{EffectiveDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Group_Gift_Effective_Liability)
### Request Fields (**bold** fields required)
| Field                          | Type    | Description              | Location |
|--------------------------------|---------|--------------------------|----------|
| **Id**                         | Integer | Group Id.                | URL      |
| **EffectiveDate** <sup>1</sup> | Date    | Liability as of beginning of this day. | URL      |

<sup>1</sup> Date format is yyyy-MM-dd.<br />

### Response JSON
```
[  
   {  
      "Account":"8383830000000034",
      "Balance":"25.00"
   },
   {  
      "Account":"8383830000000042",
      "Balance":"113.00"
   }
]
```
<br />

## Groups Reconcile
Net change in liability for the date range partitioned by business<br />

`GET` [/v1/storedvalue/groups/**{Id}**/reconcile?StartDate=**{StartDate}**&EndDate=**{EndDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Group_Gift_Reconciliation)

### Request Fields (**bold** fields required)
| Field                         | Type    | Description              | Location |
|-------------------------------|---------|--------------------------|----------|
| **Id**                        | Integer | Group Id.                | URL      |
| **StartDate** <sup>1</sup>    | Date    | Start date               | URL      |
| **EndDate** <sup>1</sup>      | Date    | End date                 | URL      |

<sup>1</sup> Date format is yyyy-MM-dd.<br />

### Response JSON
```
[
   {
      "BusinessId": 555,
      "Business": "Dgo - Main Location",
      "Amount": 800,
	  "IsHoldingBusiness": 1
   },
   {
      "BusinessId": 123,
      "Business": "Den - Cherry Creek Location",
      "Amount": -5,
	  "IsHoldingBusiness": 0
   }
]
```
<br />

## Groups Transactions
Transactions in the date range for group owned accounts<br />

`GET` [/v1/storedvalue/groups/**{Id}**/transactions?StartDate=**{StartDate}**&EndDate=**{EndDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Group_Gift_Transactions)

### Request Fields (**bold** fields required)
| Field                         | Type    | Description              | Location |
|-------------------------------|---------|--------------------------|----------|
| **Id**                        | Integer | Group Id.                | URL      |
| **StartDate** <sup>1</sup>    | Date    | Start date               | URL      |
| **EndDate** <sup>1</sup>      | Date    | End date                 | URL      |

<sup>1</sup> Date format is yyyy-MM-dd.<br />

### Response JSON
```
[
   {
      "BusinessId": 555,
      "Business": "Dgo - Main Location",
      "Amount": 800
   },
   {
      "BusinessId": 123,
      "Business": "Den - Cherry Creek Location",
      "Amount": -5
   }
]```
<br />
