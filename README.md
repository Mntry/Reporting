# Getting Started with Reporting API
###Authorization

Authorization is easy, just insert your secret key in the `Authorization` header:

`Authorization: secretKEYGOESHERE`
  
###Content Types
Communicate with us in your favorite content type!

We support the following for `Content-Type` and `Accepts` values:

* `application/json`

##Transactions

###[Stored Value Reports](STOREDVALUE.md)
* [Business Reconcile](STOREDVALUE.md#load) `POST` /storedvalue/load
* [Business Liability Current](STOREDVALUE.md#void-load) `POST` /storedvalue/load/**{RefNo}**/void
* [Business Liability Effective](STOREDVALUE.md#sale) `POST` /storedvalue/sale

###Success Responses
* ```200 OK``` Approved Transaction

###Failure Responses
* ```400 BAD REQUEST``` Invalid Transaction Request
* ```401 UNAUTHORIZED``` Unauthorized Transaction

###Example Credit Sale Request

```
POST https://pay.monetary.co/v1/credit/sale

Authorization: secretKEYGOESHERE
Content-Type: application/json
Accept: application/json

{
  "Amount": "1.00",
  "Account": "4242424242424242",
  "Expiration": "1220"
}
```

###Example Credit Sale Response
```
200 OK

{
  "Status": "Approved",
  "Message": "APPROVAL",
  "Account": "XXXXXXXXXXXX4242",
  "Expiration": "XXXX",
  "Brand": "VISA",
  "RefNo": "123",
  "Amount": "1.00",
  "Authorized": "1.00",
  "Token": "card_1ABCDEFG2"
}
```
