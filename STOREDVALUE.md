
# Monetary Reporting API

### Stored Value Reporting Requests
* [Account Transactions](#account-transactions)
* [Business Credit Current](#business-credit-current)
* [Business Credit Effective](#business-credit-effective)
* [Business Liability Current](#business-liability-current)
* [Business Liability Effective](#business-liability-effective)
* [Business Reconcile](#business-reconcile)
* [Business Transactions](#business-transactions)
* [Groups Credit Current](#groups-credit-current)
* [Groups Credit Effective](#groups-credit-effective)
* [Groups Liability Current](#groups-liability-current)
* [Groups Liability Effective](#groups-liability-effective)
* [Groups Reconcile](#groups-reconcile)
* [Groups Transactions](#groups-transactions)

## Account Transactions
All transactions for a single stored value account<br />

`GET` [/v1/storedvalue/**{Id}**/transactions](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Stored_Value_Account_Transactions)

### Request Fields (**bold** fields required)
| Field                         | Type    | Description              | Location |
|-------------------------------|---------|--------------------------|----------|
| **Id**                        | number  | SV Account Number        | URL      |

### Response JSON
```
[
   {
      "Reference": 102394,
      "DatetimeLocal": "2018-01-31T12:10:49.84",
      "Trancode": "Sale",
      "Status": "Approved",
      "Message": null,
      "Invoice": "T3HB1LLS",
      "Account": "8383830000000018",
      "Amount": -5.95,
      "IsBulk": false,
      "IsPromo": false,
      "VoidId": null,
      "Business": "Dgo - Main Location"
   },
   {
      "Reference": null,
      "DatetimeLocal": "2018-01-31T12:10:49.84",
      "Trancode": "Set",
      "Status": "Error",
      "Message": "Invalid Account/CVV/Identifier",
      "Invoice": null,
      "Account": "8282820000001894",
      "Amount": null,
      "IsBulk": false,
      "IsPromo": false,
      "VoidId": null,
      "Business": "Den - Cherry Creek Location"
   }
]
```
<br />

## Business Credit Current
Current credit on business owned accounts<br />

`GET` [/v1/storedvalue/creditCurrent](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Single_Location_Stored_Value_Current_Credit)

### Response JSON
```
[  
   {  
      "Account":"8383830000000034",
      "Balance":"-225.00"
   },
   {  
      "Account":"8383830000000042",
      "Balance":"-113.00"
   }
]
```
<br />

## Business Credit Effective
Credit as of effective date on business owned accounts<br />

`GET`  [/v1/storedvalue/creditEffective?EffectiveDate=**{EffectiveDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Single_Location_Stored_Value_Effective_Credit)

### Request Fields (**bold** fields required)
| Field                          | Type    | Description              | Location |
|--------------------------------|---------|--------------------------|----------|
| **EffectiveDate** <sup>1</sup> | Date    | Credit as of beginning of this day. | URL      |

<sup>1</sup> Date format is yyyy-MM-dd.<br />

### Response JSON
```
[  
   {  
      "Account":"8383830000000034",
      "Balance":"-25.00"
   },
   {  
      "Account":"8383830000000042",
      "Balance":"-113.00"
   }
]
```
<br />

## Business Liability Current
Current liability on business owned accounts<br />

`GET` [/v1/storedvalue/liabilityCurrent](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Single_Location_Stored_Value_Current_Liability)

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

`GET`  [/v1/storedvalue/liabilityEffective?EffectiveDate=**{EffectiveDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Single_Location_Stored_Value_Effective_Liability)

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

`GET` [/v1/storedvalue/reconcile?StartDate=**{StartDate}**&EndDate=**{EndDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Single_Location_Stored_Value_Reconciliation)

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

`GET` [/v1/storedvalue/transactions?StartDate=**{StartDate}**&EndDate=**{EndDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Single_Location_Stored_Value_Transactions)

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

## Groups Credit Current
Current credit on group owned accounts<br />

`GET` [/v1/storedvalue/groups/**{id}**/creditCurrent](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Group_Stored_Value_Current_Credit)

### Request Fields (**bold** fields required)
| Field                          | Type    | Description              | Location |
|--------------------------------|---------|--------------------------|----------|
| **Id**                         | Integer | Group Id.                | URL      |


### Response JSON
```
[  
   {  
      "Account":"8383830000000034",
      "Balance":"-225.00"
   },
   {  
      "Account":"8383830000000042",
      "Balance":"-113.00"
   }
]
```
<br />

## Groups Credit Effective
Credit as of effective date on group owned accounts<br />

`GET` [/v1/storedvalue/groups/**{Id}**/creditEffective?EffectiveDate=**{EffectiveDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Group_Stored_Value_Effective_Credit)
### Request Fields (**bold** fields required)
| Field                          | Type    | Description              | Location |
|--------------------------------|---------|--------------------------|----------|
| **Id**                         | Integer | Group Id.                | URL      |
| **EffectiveDate** <sup>1</sup> | Date    | Credit as of beginning of this day. | URL      |

<sup>1</sup> Date format is yyyy-MM-dd.<br />

### Response JSON
```
[  
   {  
      "Account":"8383830000000034",
      "Balance":"-25.00"
   },
   {  
      "Account":"8383830000000042",
      "Balance":"-113.00"
   }
]
```
<br />

## Groups Liability Current
Current liability on group owned accounts<br />

`GET` [/v1/storedvalue/groups/**{id}**/liabilityCurrent](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Group_Stored_Value_Current_Liability)

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

`GET` [/v1/storedvalue/groups/**{Id}**/liabilityEffective?EffectiveDate=**{EffectiveDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Group_Stored_Value_Effective_Liability)
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

`GET` [/v1/storedvalue/groups/**{Id}**/reconcile?StartDate=**{StartDate}**&EndDate=**{EndDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Group_Stored_Value_Reconciliation)

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

`GET` [/v1/storedvalue/groups/**{Id}**/transactions?StartDate=**{StartDate}**&EndDate=**{EndDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Group_Stored_Value_Transactions)

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
      "Reference": 102394,
      "DatetimeLocal": "2018-01-31T12:10:49.84",
      "Trancode": "Sale",
      "Status": "Approved",
      "Message": null,
      "Invoice": "T3HB1LLS",
      "Account": "8383830000000018",
      "Amount": -5.95,
      "IsBulk": false,
      "IsPromo": false,
      "VoidId": null,
      "BusinessID": 555,
      "Business": "Dgo - Main Location"
   },
   {
      "Reference": null,
      "DatetimeLocal": "2018-01-31T12:10:49.84",
      "Trancode": "Set",
      "Status": "Error",
      "Message": "Invalid Account/CVV/Identifier",
      "Invoice": null,
      "Account": "8282820000001894",
      "Amount": null,
      "IsBulk": false,
      "IsPromo": false,
      "VoidId": null,
      "BusinessID": 123,
      "Business": "Den - Cherry Creek Location"
   }
]
```
<br />
