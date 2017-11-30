## Pass Messages, Not Objects

_Client and Server SHOULD NOT share internal object or data models. 
Instead, message bodies SHOULD be sent using a highly-structured metadata-rich format such as:_
 
 * HAL
 * Collection+JSON
 * Siren
 * UBER
 * Atom
 * etc.
 
 ## Server-Side Example
 
 ```javascript
 
 var responseObject = {};
 var messageBody = "";
 responseObject.customerSummary = dataStore.getCustomerSummary(custId);
 responseObject.outstandingInvoices = dataStore.getInvoices(custId,status="outstanding");
 responseObject.shippingStatus = dataStore.getOrdersInTransit(custId);
 
 messageBody = messageTranslator(responseObject,"application/HTML");
 HTTP.Send(messageBody);
 
 ```
