
# Monetary Reporting API

### Stored Value Reporting Requests
* [Business Reconcile](#business-reconcile)
* [Business Liability Current](#business-liability-current)
* [Business Liability Effective](#business-liability-effective)

## Business Reconcile

`GET` /storedvalue/business/reconcile?StartDate=**{StartDate}**&EndDate=**{EndDate}**

###Request Fields (**bold** fields required)
| Field                         | Type    | Description              | Location |
|-------------------------------|---------|--------------------------|----------|
| **StartDate** <sup>1</sup>    | Date    | Start date               | URL      |
| **EndDate** <sup>1</sup>      | Date    | End date                 | URL      |

<sup>1</sup> Date format is yyyy-MM-dd.<br />

###Response JSON
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

## Business Liability Current <sup>*</sup>

`GET` /storedvalue/business/liabilityCurrent

<sup>*</sup> Reports on business owned accounts.<br />

###Response JSON
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

## Business Liability Effective <sup>*</sup>

`GET` /storedvalue/business/liabilityeffective?EffectiveDate=**{EffectiveDate}**

<sup>*</sup> Reports on business owned accounts.<br />

###Request Fields (**bold** fields required)
| Field                          | Type    | Description              | Location |
|--------------------------------|---------|--------------------------|----------|
| **EffectiveDate** <sup>1</sup> | Date    | Liability as of beginning of this day. | URL      |

<sup>1</sup> Date format is yyyy-MM-dd.<br />

###Response JSON
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
