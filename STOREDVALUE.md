
# Monetary Reporting API

### Stored Value Reporting Requests
* [Account Transactions](#account-transactions)
* [Business Reconcile](#business-reconcile)
* [Business Liability Current](#business-liability-current)
* [Business Liability Effective](#business-liability-effective)
* [Groups Liability Current](#groups-liability-current)
* [Groups Liability Effective](#groups-liability-effective)

## Account Transactions
Retrieve all transactions for a single stored value account
`GET` [/v1/storedvalue/**{Id}**/transactions](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/StoredValue_AccountTransactions)

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

## Business Reconcile

`GET` [/v1/storedvalue/reconcile?StartDate=**{StartDate}**&EndDate=**{EndDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/StoredValue_BusinessReconcile)

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

## Business Liability Current
Reports on business owned accounts.<br />

`GET` [/v1/storedvalue/liabilityCurrent](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/StoredValue_BusinessLiabilityCurrent)

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
Reports on business owned accounts.<br />

`GET`  [/v1/storedvalue/liabilityEffective?EffectiveDate=**{EffectiveDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/StoredValue_BusinessLiabilityEffective)

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

## Groups Liability Current
Reports on group owned accounts.<br />

`GET` [/v1/storedvalue/groups/**{id}**/liabilityCurrent](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/StoredValue_GroupsLiabilityCurrent)

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
Reports on group owned accounts.<br />

`GET` [/v1/storedvalue/groups/**{Id}**/liabilityEffective?EffectiveDate=**{EffectiveDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/StoredValue_GroupsLiabilityEffective)
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
