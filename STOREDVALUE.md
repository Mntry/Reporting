
# Monetary Reporting API

### Stored Value Reporting Requests
* [Business Reconcile](#business-reconcile)
* [Business Liability Current](#business-liability-current)
* [Business Liability Effective](#business-liability-effective)
* [Groups Liability Current](#groups-liability-current)
* [Groups Liability Effective](#groups-liability-effective)

## Business Reconcile

`GET` /v1/storedvalue/business/reconcile?StartDate=**{StartDate}**&EndDate=**{EndDate}**

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

`GET` /v1/storedvalue/business/liabilityCurrent

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

`GET` /v1/storedvalue/business/liabilityEffective?EffectiveDate=**{EffectiveDate}**

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

`GET` /v1/storedvalue/groups/**{Id}**/liabilityCurrent

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

`GET` /v1/storedvalue/groups/**{Id}**/liabilityEffective?EffectiveDate=**{EffectiveDate}**

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
