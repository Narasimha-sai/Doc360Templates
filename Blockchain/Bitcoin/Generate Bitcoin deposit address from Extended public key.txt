## Generate Bitcoin deposit address from Extended public key
**1 credit per API call.**

Generates a Bitcoin deposit address from an Extended public key. The deposit address is generated for the specific index - each extended public key can generate up to 2^31 addresses starting from index 0 until 2^31 - 1.


|  AUTHORIZATIONS: | api_token |
| --- | --- |

:::(Warning) 
| QUERY PARAMETERS | 
| --- | 

|  PARAMETERS |    TYPE     |       DESCRIPTION |
| --- | --- | --- |
| xpub (required) | string | Example: xpub6EsCk1uU6cJzqvP9CdsTiJwT2rF748YkPnhv5Qo8q44DG7nn2vbyt48YRsNSUYS44jFCW9gwvD9kLQu9AuqXpTpM1c5hgg9PsuBLdeNncid Extended public key of a wallet. |
|   index (required) | number >= 0 |    Example: 1 Derivation index of the desired address to be generated.   |
:::
## Method
:::(Info) (GET)
:::

## URL  
``` endpoint
https://api-eu1.tatum.io/v3/bitcoin/address/{xpub}/{index}
```
### Request Samples
:::(Warning) 
```cURL
curl --request GET \
  --url https://api-eu1.tatum.io/v3/bitcoin/address/{xpub}/{index} \
  --header 'x-api-key: REPLACE_KEY_VALUE'
```     
``` Node
const http = require("https");

const options = {
  "method": "GET",
  "hostname": "api-eu1.tatum.io",
  "port": null,
  "path": "/v3/bitcoin/address/{xpub}/{index}",
  "headers": {
    "x-api-key": "REPLACE_KEY_VALUE"
  }
};

const req = http.request(options, function (res) {
  const chunks = [];

  res.on("data", function (chunk) {
    chunks.push(chunk);
  });

  res.on("end", function () {
    const body = Buffer.concat(chunks);
    console.log(body.toString());
  });
});

req.end();
```
``` JAVA
HttpResponse<String> response = Unirest.get("https://api-eu1.tatum.io/v3/bitcoin/address/{xpub}/{index}")
  .header("x-api-key", "REPLACE_KEY_VALUE")
  .asString();
```
``` Go
package main

import (
	"fmt"
	"net/http"
	"io/ioutil"
)

func main() {

	url := "https://api-eu1.tatum.io/v3/bitcoin/address/{xpub}/{index}"

	req, _ := http.NewRequest("GET", url, nil)

	req.Header.Add("x-api-key", "REPLACE_KEY_VALUE")

	res, _ := http.DefaultClient.Do(req)

	defer res.Body.Close()
	body, _ := ioutil.ReadAll(res.Body)

	fmt.Println(res)
	fmt.Println(string(body))

}
```
``` PHP
<?php

$curl = curl_init();

curl_setopt_array($curl, [
  CURLOPT_URL => "https://api-eu1.tatum.io/v3/bitcoin/address/{xpub}/{index}",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "GET",
  CURLOPT_HTTPHEADER => [
    "x-api-key: REPLACE_KEY_VALUE"
  ],
]);

$response = curl_exec($curl);
$err = curl_error($curl);

curl_close($curl);

if ($err) {
  echo "cURL Error #:" . $err;
} else {
  echo $response;
}
```
``` Python3
import http.client

conn = http.client.HTTPSConnection("api-eu1.tatum.io")

headers = { 'x-api-key': "REPLACE_KEY_VALUE" }

conn.request("GET", "/v3/bitcoin/address/{xpub}/{index}", headers=headers)

res = conn.getresponse()
data = res.read()

print(data.decode("utf-8"))
```
```C
CURL *hnd = curl_easy_init();

curl_easy_setopt(hnd, CURLOPT_CUSTOMREQUEST, "GET");
curl_easy_setopt(hnd, CURLOPT_URL, "https://api-eu1.tatum.io/v3/bitcoin/address/{xpub}/{index}");

struct curl_slist *headers = NULL;
headers = curl_slist_append(headers, "x-api-key: REPLACE_KEY_VALUE");
curl_easy_setopt(hnd, CURLOPT_HTTPHEADER, headers);

CURLcode ret = curl_easy_perform(hnd);
```
``` C-sharp
var client = new RestClient("https://api-eu1.tatum.io/v3/bitcoin/address/{xpub}/{index}");
var request = new RestRequest(Method.GET);
request.AddHeader("x-api-key", "REPLACE_KEY_VALUE");
IRestResponse response = client.Execute(request);
```
``` Javascript-JQuery
const settings = {
  "async": true,
  "crossDomain": true,
  "url": "https://api-eu1.tatum.io/v3/bitcoin/address/{xpub}/{index}",
  "method": "GET",
  "headers": {
    "x-api-key": "REPLACE_KEY_VALUE"
  }
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
``` Objective-C
#import <Foundation/Foundation.h>

NSDictionary *headers = @{ @"x-api-key": @"REPLACE_KEY_VALUE" };

NSMutableURLRequest *request = [NSMutableURLRequest requestWithURL:[NSURL URLWithString:@"https://api-eu1.tatum.io/v3/bitcoin/address/{xpub}/{index}"]
                                                       cachePolicy:NSURLRequestUseProtocolCachePolicy
                                                   timeoutInterval:10.0];
[request setHTTPMethod:@"GET"];
[request setAllHTTPHeaderFields:headers];

NSURLSession *session = [NSURLSession sharedSession];
NSURLSessionDataTask *dataTask = [session dataTaskWithRequest:request
                                            completionHandler:^(NSData *data, NSURLResponse *response, NSError *error) {
                                                if (error) {
                                                    NSLog(@"%@", error);
                                                } else {
                                                    NSHTTPURLResponse *httpResponse = (NSHTTPURLResponse *) response;
                                                    NSLog(@"%@", httpResponse);
                                                }
                                            }];
[dataTask resume];
```
``` Ocaml
open Cohttp_lwt_unix
open Cohttp
open Lwt

let uri = Uri.of_string "https://api-eu1.tatum.io/v3/bitcoin/address/{xpub}/{index}" in
let headers = Header.add (Header.init ()) "x-api-key" "REPLACE_KEY_VALUE" in

Client.call ~headers `GET uri
>>= fun (res, body_stream) ->
  (* Do stuff with the result *)
```
``` Ruby
require 'uri'
require 'net/http'
require 'openssl'

url = URI("https://api-eu1.tatum.io/v3/bitcoin/address/{xpub}/{index}")

http = Net::HTTP.new(url.host, url.port)
http.use_ssl = true
http.verify_mode = OpenSSL::SSL::VERIFY_NONE

request = Net::HTTP::Get.new(url)
request["x-api-key"] = 'REPLACE_KEY_VALUE'

response = http.request(request)
puts response.read_body
```
``` Swift
import Foundation

let headers = ["x-api-key": "REPLACE_KEY_VALUE"]

let request = NSMutableURLRequest(url: NSURL(string: "https://api-eu1.tatum.io/v3/bitcoin/address/{xpub}/{index}")! as URL,
                                        cachePolicy: .useProtocolCachePolicy,
                                    timeoutInterval: 10.0)
request.httpMethod = "GET"
request.allHTTPHeaderFields = headers

let session = URLSession.shared
let dataTask = session.dataTask(with: request as URLRequest, completionHandler: { (data, response, error) -> Void in
  if (error != nil) {
    print(error)
  } else {
    let httpResponse = response as? HTTPURLResponse
    print(httpResponse)
  }
})

dataTask.resume()
```
:::
##  Response samples
:::(Info) (200)

| content type | application/json |
| --- | --- |
```json
{
  "address": "n36h3pAH7sC3z8KMB47BjbqvW2aJd2oTi7"
}
```
:::
:::(Error) (400)

| content type | application/json |
| --- | --- |
```json
{
  "errorCode": "validation.failed",
  "message": "Request validation failed. Please see data for additional information.",
  "statusCode": 400,
  "data": [
    {
      "target": {
        "property": 12345
      },
      "value": 12345,
      "property": "property1",
      "constraints": {
        "min": "property1 must not be less than 50000"
      }
    }
  ]
}
```
:::
:::(Error) (401)

| content type | application/json |
| --- | --- |

|  Example | Error401NotActive |
| --- | --- |
```json
{
  "errorCode": "subscription.not.active",
  "message": "Subscription not active anymore.",
  "statusCode": 401
}
```
|  Example | Error401Invalid |
| --- | --- |

```json
{
  "errorCode": "subscription.invalid",
  "message": "Unable to find valid subscription for '${apiKey}'",
  "statusCode": 401
}
```
:::
:::(Error) (403)

| content type | application/json |
| --- | --- |

| Example |Error403AccountIncompatibleXpubBtc |
| --- | --- |
```json
{
  "errorCode": "address.generation.failed.wrong.xpub",
  "message": "Unable to generate address, wrong xpub and account type.",
  "statusCode": 403
}
```
|Example|    Error403AccountAddressGeneral |
| --- | --- |
```json
{
  "errorCode": "address.generation.failed",
  "message": "Unable to generate address.",
  "statusCode": 403
}
```
:::

:::(Error) (500)

| content type | application/json |
| --- | --- |
```json
{
  "message": "Internal server error",
  "statusCode": 500
}
```
:::

## Responses
:::(Info) (200 OK)
| RESPONSE SCHEMA:  | application/json |
| --- | --- |

| Parameters | Type | Description|
| --- | --- | --- |
| address | string | Bitcoin address|

:::
:::(Error) (400 Bad Request. Validation failed for the given object in the HTTP Body or Request parameters.)

| RESPONSE SCHEMA:  | application/json |
| --- | --- |

| Parameters | | | Type | Description |
| --- | --- | --- | --- | --- |
| errorCode (required) ||| string | validation.failed |
| message (required)||| string | Request validation failed. Please see data for additional information. |
|statusCode (required) ||| number | 400 |
|data (required) |||Array of objects ||
|  | target (required)  |   | object  | Request object present in the body of the HTTP request  |
|   |   | property name*  | any  |   |  
| | value  |   | number  | Value of the target object which validation is wrong. Can be of any data type, example here is using type number. |
||  property ||string|Property name of the target object which validation is wrong|	
| | constraints ||object|Object of failed constraints for the target object. Key is the constraint, value is detailed description of the failed constraint.|
|   |   | property name*  | any  |   |


:::

:::(Error) (401 Unauthorized. Not valid or inactive subscription key present in the HTTP Header.)

| RESPONSE SCHEMA:  | application/json |
| --- | --- |

| Error401NotActive |
| --- |


| Parameter | Type | Description |
| --- | --- | --- |
| errorCode (required) | string | subscription.not.active |
| message (required) | string | Subscription not active anymore. |
| statusCode (required) | number | 401 |

| Error401Invalid |
| --- |


| Parameter | Type | Description |
| --- | --- | --- |
| errorCode (required)|string|subscription.invalid|
| message (required) | string |Unable to find valid subscription for '${apiKey}'|
| statusCode (required) | number | 401 |

:::

:::(Error) (403 Forbidden. The request is authenticated, but it is not possible to perform the required operation due to a logical error or invalid permissions.)

| RESPONSE SCHEMA:  | application/json |
| --- | --- |

| Error403AccountIncompatibleXpubBtc |
| --- |

| Parameter | Type | Description |
| --- | --- | --- |
| errorCode (required) | string | Address.generation.failed.wrong.xpub |
|message (required) | string | Unable to generate address, wrong xpub and account type. |
| statusCode (required) | number | 403 |

| Error403AccountAddressGeneral|
| --- |

| Parameters | Type | Description |
| --- | --- | --- |
| errorCode (required) | string | Address.generation.failed |
| message (required) | string | Unable to generate address. |
| statusCode (required) |  number | 403 | 
:::

:::(Error) (500 Internal server error. There was an error on the server while processing the request.)
| RESPONSE SCHEMA:  | application/json |
| --- | --- |

| Parameter | Type | Description |
| --- | --- | --- |
| message (required) | string | Internal server error|
| statusCode (required) | number | 500 |
:::

