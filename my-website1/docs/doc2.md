---
id: doc2
title: API Methods
---

Below is a brief summary of the indispensable methods of the Gestopago API. After this list, each one of them will be described in detail, including methods that do not participate directly in the sales flow.

## sendEcho
This method validates the Token send on the authorization header and if it’s correct returns the “codigoDispositivo” value of the commerce.  This method can be used to test and measure connectivity to Gestopago.

## validateMe
This method validates the Token send on the authorization header and if it’s correct returns the commerce Information.

## getProductList
This method obtains the list of services and products that the distributor is authorized to sell. It is a method that allows the integrator to save in their database the product/service ID's, which they will use in the sendTx method and confirmTx

## sendTx
This method is used to make a sale of any type of product/service. To use this method it is necessary to know the tipoFront of the product so that the integrator knows what are the parameters that the API will be waiting for that product. At the moment 4 different types of front are identified, which are explained in greater detail below.
The sendTx method could return success or failure in his invocation, in the case of failure is requested to map the error codes for the correct interpretation. The current error table is detailed below.

## confirmTx
When the sendTx.do method does not return any result (failure or success) either for a timeout or for some type of disconnection that makes it impossible for the implementer to receive the sale response, ** _it is obligatory to execute the confirmTx method with exactly the same parameters previously used in sendTx.do_**.

This method has the goal of recovering the final status of the transaction by returning if it was successful or not. The most important consideration for the execution of this method is that **_it should not be executed before 62 seconds_** of having sent the sendTx, since if it was sent before this time it could return that the operation was not completed when the natural lifetime of the operation is 62 seconds.

## getBalance
This method allows the integrator to know the balance of his prepaid bag, so he can have his own platform updated with the remaining balance.

## API FLOW  GESTOPAGO

![img](../static/img/API_FLOW.png)
