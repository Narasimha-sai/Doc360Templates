## Heading
**credit**

description


|  AUTHORIZATIONS: | api_token |
| --- | --- |

:::(Warning) 
| PATH PARAMETERS  | 
| --- | 

|  PARAMETERS |    TYPE     |       DESCRIPTION |
| --- | --- | --- |
| cell | cell | cell |


| REQUEST BODY SCHEMA  | application/json |
| --- | --- |

|  PARAMETERS |    TYPE     |       DESCRIPTION |
| --- | --- | --- |
| cell | cell | cell |
:::
## Method
:::(Info) (PUT)
:::

## URL  
``` endpoint
endpoint
```
### Request Samples
:::(Warning) 
```cURL

```     
``` Node

```
``` JAVA

```
``` Go

```
``` PHP

```
``` Python3

```
```C

```
``` C-sharp

```
``` Javascript-JQuery

```
``` Objective-C

```
``` Ocaml

```
``` Ruby

```
``` Swift

```
:::
##  Response samples

:::(Error) (400)

| content type | application/json |
| --- | --- |
```json

```
:::
:::(Error) (401)

| content type | application/json |
| --- | --- |
```json

```
:::
:::(Error) (403)

| content type | application/json |
| --- | --- |
```json

```
:::

:::(Error) (500)

| content type | application/json |
| --- | --- |
```json

```
:::

## Responses
:::(Info) (204 OK)

:::
:::(Error) (400 Bad Request. Validation failed for the given object in the HTTP Body or Request parameters.)

| RESPONSE SCHEMA:  | application/json |
| --- | --- |


| Parameters | Type | Description |
| --- | --- | --- |
| cell | cell | cell |
| cell | cell | cell |

:::

:::(Error) (401 Unauthorized. Not valid or inactive subscription key present in the HTTP Header.)

| RESPONSE SCHEMA:  | application/json |
| --- | --- |

:::

:::(Error) (403 Forbidden. The request is authenticated, but it is not possible to perform the required operation due to a logical error or invalid permissions.)

| RESPONSE SCHEMA:  | application/json |
| --- | --- |

:::

:::(Error) (500 Internal server error. There was an error on the server while processing the request.)
| RESPONSE SCHEMA:  | application/json |
| --- | --- |

:::



