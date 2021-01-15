---
id: doc1
title: GestoPago API
sidebar_label: GestoPago API
slug: /
---
GestoPago provides a Web-API with which it is possible the interconnection of many types of clients to consume electronic services, entertainment, prepaid services, and process payments.

## Security Pipe

The system has HTTPS implemented, which ensures the transfer of customer data to Gestopago servers.

## Security headers

For more details check the pdf `GPS_API_Security_V2.0.2.pdf`

## Security on payload

The submission of the payload used in each API method must be sent encrypted using **AES256**. 
The list of parameters must be set up in JSON to be subsequently encrypted using a key previously provided to the implementer.
For more details check the pdf  `GPS_API_Security_V2.0.pdf `

## General context

For the use of this API it is necessary that the distributor is correctly registered in the Sales Portal, having completed the following steps:

1. Distributor Registration.
1. Registration of device (s) through which you will have connection with the Portal Sales, these can be, web console, point of sale, mobile device etc.
1. Prepaid distributor balance.
1. Registration of services that the distributor may offer

## Log evidence 

It is the obligation of the implementer to save the requests and responses that are exchanged between Gestopago and the implementer server in some type of log. The log can be a file or database, but it is necessary to have the data that is sent and received for any type of revision or clarification.

## IP restriction(optional)

If the implementer needs it they can give it to Gestopago a set IP's for interaction with the Gestopago API. The platform will only allow the interaction of commerce through this IP.

## Timeout

It is the maximum waiting time that API requests should have. ** _Currently the value is 62 seconds_**.

