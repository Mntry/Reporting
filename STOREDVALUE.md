
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
[{"GroupId":1,"Group":"Bark & Meow","Amount":"-11.23"}]
```
<br />

## Business Liability Current

`GET` /storedvalue/business/liabilityCurrent

###Request Fields (**bold** fields required)
N/A

###Response JSON
```
[{"Account":"","Balance":"-11.23"},{"Account":"","Balance":"-11.23"},{"Account":"","Balance":"-11.23"}]
```
<br />

## Business Liability Effective

`GET` /storedvalue/business/liabilityEffective?EffectiveDate=**{EffectiveDate}**

###Request Fields (**bold** fields required)
| Field                          | Type    | Description              | Location |
|--------------------------------|---------|--------------------------|----------|
| **EffectiveDate** <sup>1</sup> | Date    | Effective date           | URL      |

<sup>1</sup> Date format is yyyy-MM-dd.<br />

###Response JSON
```
[{"Account":"","Balance":"-11.23"},{"Account":"","Balance":"-11.23"},{"Account":"","Balance":"-11.23"}]
```
<br />
