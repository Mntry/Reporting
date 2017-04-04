# Getting Started with Reporting API
### Authorization

Authorization is easy, just insert your secret key in the `Authorization` header:

`Authorization: secretKEYGOESHERE`
  
### Content Types
We support the following for `Content-Type` and `Accepts` values:

* `application/json`

### [Groups Reports](GROUPS.md)

* [Groups](GROUPS.md#groups) `GET` /v1/groups

### [Stored Value Reports](STOREDVALUE.md)

* [Business Reconcile](STOREDVALUE.md#business-reconcile) `GET` /v1/storedvalue/business/reconcile?StartDate=**{StartDate}**&EndDate=**{EndDate}**
* [Business Liability Current](STOREDVALUE.md#business-liability-current) `GET` /v1/storedvalue/business/liabilityCurrent
* [Business Liability Effective](STOREDVALUE.md#business-liability-effective) `GET` /v1/storedvalue/business/liabilityEffective?EffectiveDate=**{EffectiveDate}**
* [Groups Liability Current](STOREDVALUE.md#groups-liability-current) `GET` /v1/storedvalue/groups/**{id}**/liabilityCurrent
* [Groups Liability Effective](STOREDVALUE.md#groups-liability-effective) `GET` /v1/storedvalue/groups/**{Id}**/liabilityEffective?EffectiveDate=**{EffectiveDate}**

### Success Responses

* ```200 OK```

### Failure Responses

* ```400 BAD REQUEST```
* ```401 UNAUTHORIZED```
* ```404 NOT FOUND```

### Example Stored Value Business Reconcile Request

```
GET https://reporting.monetary.co/v1/storedvalue/business/reconcile?StartDate=2016-10-1&EndDate=2016-10-31

Authorization: secretKEYGOESHERE
Content-Type: application/json
Accept: application/json
```

### Example Stored Value Business Reconcile Response
```
200 OK

[
   {  
      "GroupId":1,
      "Group":"Bark & Meow",
      "Amount":"-11.23"
   }
]
```
