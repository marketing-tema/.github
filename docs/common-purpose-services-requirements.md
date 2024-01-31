# Requirements

## Common purpose services

### Exchange Interactor
Allows interaction with any exchange via versatile API. Abstraction over concrete exchanges.

#### Purpose
Exchange Interactor is a configurable service which is responsible for polling echanges APIs 
and performing transfer and order operations agains specified exchanges. It encapsulates requests' complexity 
and access control to exchnages.

One should be able to subscribe on data provided by polling exchanges by specifing subscription mechanism (grpc/MQ)
tokens of interest and etc. 

### Data Bucket

#### Purpose
Data Bucket is a configurable history storage. It stores order books, candlesticks and etc.

In order to pull data it should be subscribed on exchange interactor.

To regulate polling rate dosen of settings should be available.

#### Non-functional requirements
1. Durable -- 
1. Quickly available recent data

## Finance service
### Purpose

### Requirements
#### Functional requirements
1. Must transfer currency from one exchange to another
1. Must place orders limit/market for provided exchange and token
1. Must support transfer and order approval if needed

#### Non-Functional requirements
1. Observability: any operation request, result or error must be persisted for later usage
1. Reliability: no operation can get lost or left unhandled

### Configuration service
#### Purpose
With global configuration service one can adjust settings of registered services

### Notification service
#### Purpose
Notification service should send messages using various intermediates

