# Getting Started with Reporting API
### Authorization

Authorization is easy, just insert your secret key in the `Authorization` header:

`Authorization: secretKEYGOESHERE`
  
### Content Types
We support the following for `Content-Type` and `Accepts` values:

* `application/json`

### [Credit Reports](CREDIT.md)

* [Credit Transactions](CREDIT.md#credit) `GET` [v1/credit/transactions](https://reporting-cert.monetary.co/swagger/ui/index#!/Credit/Credit_Transactions)

### [Groups Reports](GROUPS.md)

* [Groups](GROUPS.md#groups) `GET` [/v1/groups](https://reporting-cert.monetary.co/swagger/ui/index#!/Groups/Available_Groups)

### [Stored Value Reports](STOREDVALUE.md)
* [Account Transactions](STOREDVALUE.md#account-transactions) `GET` [/v1/storedvalue/account/{Id}/Transactions](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Stored_Value_Account_Transactions)
* [Business Liability Current](STOREDVALUE.md#business-liability-current) `GET` [/v1/storedvalue/liabilityCurrent](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Single_Location_Stored_Value_Current_Liability)
* [Business Liability Effective](STOREDVALUE.md#business-liability-effective) `GET` [/v1/storedvalue/liabilityEffective?EffectiveDate=**{EffectiveDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Single_Location_Stored_Value_Effective_Liability)
* [Business Reconcile](STOREDVALUE.md#business-reconcile) `GET` [/v1/storedvalue/reconcile?StartDate=**\{StartDate\}**&EndDate=**\{EndDate\}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Single_Location_Stored_Value_Reconciliation)
* [Business Transactions](STOREDVALUE.md#business-transactions) `GET` [/v1/storedvalue/transactions?StartDate=**\{StartDate\}**&EndDate=**\{EndDate\}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Single_Location_Stored_Value_Transactions)
* [Groups Liability Current](STOREDVALUE.md#groups-liability-current) `GET` [/v1/storedvalue/groups/**{id}**/liabilityCurrent](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Group_Stored_Value_Current_Liability)
* [Groups Liability Effective](STOREDVALUE.md#groups-liability-effective) `GET` [/v1/storedvalue/groups/**{Id}**/liabilityEffective?EffectiveDate=**{EffectiveDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Group_Stored_Value_Effective_Liability)
* [Groups Reconcile](STOREDVALUE.md#groups-reconcile) `GET` [/v1/storedvalue/groups/**{Id}**/reconcile?StartDate=**{StartDate}**&EndDate=**{EndDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Group_Stored_Value_Reconciliation)
* [Groups Transactions](STOREDVALUE.md#groups-transactions) `GET` [/v1/storedvalue/groups/**{Id}**/transactions?StartDate=**{StartDate}**&EndDate=**{EndDate}**](https://reporting-cert.monetary.co/swagger/ui/index#!/StoredValue/Group_Stored_Value_Transactions)

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
