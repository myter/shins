---
title: Weave.ly Gateway API v0.0.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="weave-ly-gateway-api">Weave.ly Gateway API v0.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

The weave.ly Gateway serves as the single external access point for all API calls to the weave.ly backend.

Base URLs:

* <a href="https://api.weave.ly">https://api.weave.ly</a>

* <a href="http://api.weave.ly">http://api.weave.ly</a>

# Authentication

- HTTP Authentication, scheme: bearer 

<h1 id="weave-ly-gateway-api-graphs">graphs</h1>

Operations on static weave.ly source code (i.e. component graphs)

## get__graphs

> Code samples

```shell
# You can also use wget
curl -X GET https://api.weave.ly/graphs \
  -H 'Accept: application/json'

```

```http
GET https://api.weave.ly/graphs HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://api.weave.ly/graphs',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.weave.ly/graphs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://api.weave.ly/graphs', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.weave.ly/graphs', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/graphs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.weave.ly/graphs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /graphs`

*Get all graphs*

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "ownerId": "string",
    "structure": {}
  }
]
```

<h3 id="get__graphs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Graphs](#schemagraphs)|

<aside class="success">
This operation does not require authentication
</aside>

## post__graphs

> Code samples

```shell
# You can also use wget
curl -X POST https://api.weave.ly/graphs \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST https://api.weave.ly/graphs HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://api.weave.ly/graphs',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post 'https://api.weave.ly/graphs',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('https://api.weave.ly/graphs', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.weave.ly/graphs', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/graphs");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.weave.ly/graphs", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /graphs`

*Create new graph*

> Example responses

> 200 Response

```json
{
  "id": "string",
  "ownerId": "string",
  "structure": {}
}
```

<h3 id="post__graphs-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Graph](#schemagraph)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearerAuth
</aside>

## get__graphs_{graphId}

> Code samples

```shell
# You can also use wget
curl -X GET https://api.weave.ly/graphs/{graphId} \
  -H 'Accept: application/json'

```

```http
GET https://api.weave.ly/graphs/{graphId} HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://api.weave.ly/graphs/{graphId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.weave.ly/graphs/{graphId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://api.weave.ly/graphs/{graphId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.weave.ly/graphs/{graphId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/graphs/{graphId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.weave.ly/graphs/{graphId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /graphs/{graphId}`

*Get graph by id*

> Example responses

> 200 Response

```json
{
  "id": "string",
  "ownerId": "string",
  "structure": {}
}
```

<h3 id="get__graphs_{graphid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[Graph](#schemagraph)|

<aside class="success">
This operation does not require authentication
</aside>

## post__graphs_{graphId}

> Code samples

```shell
# You can also use wget
curl -X POST https://api.weave.ly/graphs/{graphId} \
  -H 'Accept: application/json'

```

```http
POST https://api.weave.ly/graphs/{graphId} HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://api.weave.ly/graphs/{graphId}',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'https://api.weave.ly/graphs/{graphId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('https://api.weave.ly/graphs/{graphId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.weave.ly/graphs/{graphId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/graphs/{graphId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.weave.ly/graphs/{graphId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /graphs/{graphId}`

*Replace graph by id*

> Example responses

> 200 Response

```json
{
  "id": "string",
  "ownerId": "string",
  "structure": {}
}
```

<h3 id="post__graphs_{graphid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[Graph](#schemagraph)|

<aside class="success">
This operation does not require authentication
</aside>

## delete__graphs_{graphId}

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.weave.ly/graphs/{graphId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE https://api.weave.ly/graphs/{graphId} HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://api.weave.ly/graphs/{graphId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'https://api.weave.ly/graphs/{graphId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('https://api.weave.ly/graphs/{graphId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','https://api.weave.ly/graphs/{graphId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/graphs/{graphId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.weave.ly/graphs/{graphId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /graphs/{graphId}`

*Delete graph by id*

> Example responses

> 200 Response

```json
{
  "id": "string",
  "ownerId": "string",
  "structure": {}
}
```

<h3 id="delete__graphs_{graphid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[Graph](#schemagraph)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearerAuth
</aside>

## get__graphs_{graphId}_{field}

> Code samples

```shell
# You can also use wget
curl -X GET https://api.weave.ly/graphs/{graphId}/{field} \
  -H 'Accept: application/json'

```

```http
GET https://api.weave.ly/graphs/{graphId}/{field} HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://api.weave.ly/graphs/{graphId}/{field}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.weave.ly/graphs/{graphId}/{field}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://api.weave.ly/graphs/{graphId}/{field}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.weave.ly/graphs/{graphId}/{field}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/graphs/{graphId}/{field}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.weave.ly/graphs/{graphId}/{field}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /graphs/{graphId}/{field}`

*Get graph's field*

> Example responses

> 200 Response

```json
{
  "id": "string",
  "ownerId": "string",
  "structure": {}
}
```

<h3 id="get__graphs_{graphid}_{field}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[Graph](#schemagraph)|

<aside class="success">
This operation does not require authentication
</aside>

## post__graphs_{graphId}_{field}

> Code samples

```shell
# You can also use wget
curl -X POST https://api.weave.ly/graphs/{graphId}/{field} \
  -H 'Accept: application/json'

```

```http
POST https://api.weave.ly/graphs/{graphId}/{field} HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://api.weave.ly/graphs/{graphId}/{field}',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'https://api.weave.ly/graphs/{graphId}/{field}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('https://api.weave.ly/graphs/{graphId}/{field}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.weave.ly/graphs/{graphId}/{field}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/graphs/{graphId}/{field}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.weave.ly/graphs/{graphId}/{field}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /graphs/{graphId}/{field}`

*Write graph's field*

> Example responses

> 200 Response

```json
{
  "id": "string",
  "ownerId": "string",
  "structure": {}
}
```

<h3 id="post__graphs_{graphid}_{field}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[Graph](#schemagraph)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="weave-ly-gateway-api-sandboxes">sandboxes</h1>

Operations on weave.ly apps created through the sandbox environment

## get__sandboxes

> Code samples

```shell
# You can also use wget
curl -X GET https://api.weave.ly/sandboxes \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.weave.ly/sandboxes HTTP/1.1
Host: api.weave.ly

```

```javascript

const headers = {
  'Authorization':'Bearer {access-token}'
};

fetch('https://api.weave.ly/sandboxes',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.weave.ly/sandboxes',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://api.weave.ly/sandboxes', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.weave.ly/sandboxes', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/sandboxes");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.weave.ly/sandboxes", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /sandboxes`

*Get all sandboxes*

<h3 id="get__sandboxes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearerAuth
</aside>

## post__sandboxes

> Code samples

```shell
# You can also use wget
curl -X POST https://api.weave.ly/sandboxes \
  -H 'Accept: application/json'

```

```http
POST https://api.weave.ly/sandboxes HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://api.weave.ly/sandboxes',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'https://api.weave.ly/sandboxes',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('https://api.weave.ly/sandboxes', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.weave.ly/sandboxes', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/sandboxes");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.weave.ly/sandboxes", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /sandboxes`

*Create new sandbox*

> Example responses

> 200 Response

```json
{
  "id": 0,
  "sandboxId": "string",
  "graphId": "string",
  "ownerId": "string",
  "dataCreated": "string"
}
```

<h3 id="post__sandboxes-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[Sandbox](#schemasandbox)|

<aside class="success">
This operation does not require authentication
</aside>

## get__sandboxes_{sandboxId}

> Code samples

```shell
# You can also use wget
curl -X GET https://api.weave.ly/sandboxes/{sandboxId} \
  -H 'Accept: application/json'

```

```http
GET https://api.weave.ly/sandboxes/{sandboxId} HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://api.weave.ly/sandboxes/{sandboxId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.weave.ly/sandboxes/{sandboxId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://api.weave.ly/sandboxes/{sandboxId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.weave.ly/sandboxes/{sandboxId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/sandboxes/{sandboxId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.weave.ly/sandboxes/{sandboxId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /sandboxes/{sandboxId}`

*Get sandbox by id*

> Example responses

> 200 Response

```json
{
  "id": 0,
  "sandboxId": "string",
  "graphId": "string",
  "ownerId": "string",
  "dataCreated": "string"
}
```

<h3 id="get__sandboxes_{sandboxid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[Sandbox](#schemasandbox)|

<aside class="success">
This operation does not require authentication
</aside>

## delete__sandboxes_{sandboxId}

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.weave.ly/sandboxes/{sandboxId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE https://api.weave.ly/sandboxes/{sandboxId} HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://api.weave.ly/sandboxes/{sandboxId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'https://api.weave.ly/sandboxes/{sandboxId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('https://api.weave.ly/sandboxes/{sandboxId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','https://api.weave.ly/sandboxes/{sandboxId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/sandboxes/{sandboxId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.weave.ly/sandboxes/{sandboxId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /sandboxes/{sandboxId}`

*Delete sandbox by id*

> Example responses

> 200 Response

```json
{
  "id": 0,
  "sandboxId": "string",
  "graphId": "string",
  "ownerId": "string",
  "dataCreated": "string"
}
```

<h3 id="delete__sandboxes_{sandboxid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[Sandbox](#schemasandbox)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearerAuth
</aside>

<h1 id="weave-ly-gateway-api-componentstates">componentstates</h1>

Operation on the state of deployed weave.ly component instances

## post__componentstates

> Code samples

```shell
# You can also use wget
curl -X POST https://api.weave.ly/componentstates \
  -H 'Accept: application/json'

```

```http
POST https://api.weave.ly/componentstates HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://api.weave.ly/componentstates',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'https://api.weave.ly/componentstates',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('https://api.weave.ly/componentstates', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.weave.ly/componentstates', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/componentstates");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.weave.ly/componentstates", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /componentstates`

*Create a new component state*

> Example responses

> 200 Response

```json
{
  "componentId": "string",
  "vals": {}
}
```

<h3 id="post__componentstates-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[ComponentState](#schemacomponentstate)|

<aside class="success">
This operation does not require authentication
</aside>

## get__componentstates_{componentId}

> Code samples

```shell
# You can also use wget
curl -X GET https://api.weave.ly/componentstates/{componentId} \
  -H 'Accept: application/json'

```

```http
GET https://api.weave.ly/componentstates/{componentId} HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://api.weave.ly/componentstates/{componentId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'https://api.weave.ly/componentstates/{componentId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('https://api.weave.ly/componentstates/{componentId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.weave.ly/componentstates/{componentId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/componentstates/{componentId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.weave.ly/componentstates/{componentId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /componentstates/{componentId}`

*Get component's state by id*

> Example responses

> 200 Response

```json
{
  "componentId": "string",
  "vals": {}
}
```

<h3 id="get__componentstates_{componentid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[ComponentState](#schemacomponentstate)|

<aside class="success">
This operation does not require authentication
</aside>

## patch__componentstates_{componentId}

> Code samples

```shell
# You can also use wget
curl -X PATCH https://api.weave.ly/componentstates/{componentId} \
  -H 'Accept: application/json'

```

```http
PATCH https://api.weave.ly/componentstates/{componentId} HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://api.weave.ly/componentstates/{componentId}',
{
  method: 'PATCH',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.patch 'https://api.weave.ly/componentstates/{componentId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.patch('https://api.weave.ly/componentstates/{componentId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','https://api.weave.ly/componentstates/{componentId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/componentstates/{componentId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "https://api.weave.ly/componentstates/{componentId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /componentstates/{componentId}`

*Update part of component's state by id*

> Example responses

> 200 Response

```json
{
  "componentId": "string",
  "vals": {}
}
```

<h3 id="patch__componentstates_{componentid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[ComponentState](#schemacomponentstate)|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="weave-ly-gateway-api-measurements">measurements</h1>

Operations on measurements

## get__measurements

> Code samples

```shell
# You can also use wget
curl -X GET https://api.weave.ly/measurements \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.weave.ly/measurements HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://api.weave.ly/measurements',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.weave.ly/measurements',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://api.weave.ly/measurements', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.weave.ly/measurements', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/measurements");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.weave.ly/measurements", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /measurements`

*Get measurement based on ownerId, userId or both*

<h3 id="get__measurements-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|ownerId|query|string|false|ownerId for which measurements must be returned|
|userId|query|integer|false|userId for which measurements must be returned|

> Example responses

> 200 Response

```json
[
  {
    "measurementId": "string",
    "ownerId": "string",
    "userId": "string",
    "componentId": "string",
    "metadata": {},
    "data": {}
  }
]
```

<h3 id="get__measurements-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[Measurements](#schemameasurements)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearerAuth
</aside>

## post__measurements

> Code samples

```shell
# You can also use wget
curl -X POST https://api.weave.ly/measurements \
  -H 'Accept: application/json'

```

```http
POST https://api.weave.ly/measurements HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('https://api.weave.ly/measurements',
{
  method: 'POST',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.post 'https://api.weave.ly/measurements',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('https://api.weave.ly/measurements', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','https://api.weave.ly/measurements', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/measurements");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "https://api.weave.ly/measurements", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /measurements`

*Create new measurement*

> Example responses

> 200 Response

```json
{
  "measurementId": "string",
  "ownerId": "string",
  "userId": "string",
  "componentId": "string",
  "metadata": {},
  "data": {}
}
```

<h3 id="post__measurements-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[Measurement](#schemameasurement)|

<aside class="success">
This operation does not require authentication
</aside>

## delete__measurements

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.weave.ly/measurements \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE https://api.weave.ly/measurements HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://api.weave.ly/measurements',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'https://api.weave.ly/measurements',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('https://api.weave.ly/measurements', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','https://api.weave.ly/measurements', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/measurements");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.weave.ly/measurements", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /measurements`

*Delete measurements based on ownerId, userId or both*

<h3 id="delete__measurements-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|ownerId|query|string|false|ownerId for which measurements must be deleted|
|userId|query|integer|false|userId for which measurements must be deleted|

> Example responses

> 200 Response

```json
[
  {
    "measurementId": "string",
    "ownerId": "string",
    "userId": "string",
    "componentId": "string",
    "metadata": {},
    "data": {}
  }
]
```

<h3 id="delete__measurements-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[Measurements](#schemameasurements)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearerAuth
</aside>

## get__measurements_{measurementId}

> Code samples

```shell
# You can also use wget
curl -X GET https://api.weave.ly/measurements/{measurementId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET https://api.weave.ly/measurements/{measurementId} HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://api.weave.ly/measurements/{measurementId}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get 'https://api.weave.ly/measurements/{measurementId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('https://api.weave.ly/measurements/{measurementId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','https://api.weave.ly/measurements/{measurementId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/measurements/{measurementId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "https://api.weave.ly/measurements/{measurementId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /measurements/{measurementId}`

*Get measurement by id*

> Example responses

> 200 Response

```json
{
  "measurementId": "string",
  "ownerId": "string",
  "userId": "string",
  "componentId": "string",
  "metadata": {},
  "data": {}
}
```

<h3 id="get__measurements_{measurementid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[Measurement](#schemameasurement)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearerAuth
</aside>

## delete__measurements_{measurementId}

> Code samples

```shell
# You can also use wget
curl -X DELETE https://api.weave.ly/measurements/{measurementId} \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
DELETE https://api.weave.ly/measurements/{measurementId} HTTP/1.1
Host: api.weave.ly
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'
};

fetch('https://api.weave.ly/measurements/{measurementId}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.delete 'https://api.weave.ly/measurements/{measurementId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.delete('https://api.weave.ly/measurements/{measurementId}', headers = headers)

print(r.json())

```

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
    'Authorization' => 'Bearer {access-token}',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','https://api.weave.ly/measurements/{measurementId}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("https://api.weave.ly/measurements/{measurementId}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "https://api.weave.ly/measurements/{measurementId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /measurements/{measurementId}`

*Delete measurement by id*

> Example responses

> 200 Response

```json
{
  "measurementId": "string",
  "ownerId": "string",
  "userId": "string",
  "componentId": "string",
  "metadata": {},
  "data": {}
}
```

<h3 id="delete__measurements_{measurementid}-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|succesful operation|[Measurement](#schemameasurement)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
bearerAuth
</aside>

# Schemas

<h2 id="tocS_Graphs">Graphs</h2>
<!-- backwards compatibility -->
<a id="schemagraphs"></a>
<a id="schema_Graphs"></a>
<a id="tocSgraphs"></a>
<a id="tocsgraphs"></a>

```json
[
  {
    "id": "string",
    "ownerId": "string",
    "structure": {}
  }
]

```

An array of graph objects

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Graph](#schemagraph)]|false|none|An array of graph objects|

<h2 id="tocS_Graph">Graph</h2>
<!-- backwards compatibility -->
<a id="schemagraph"></a>
<a id="schema_Graph"></a>
<a id="tocSgraph"></a>
<a id="tocsgraph"></a>

```json
{
  "id": "string",
  "ownerId": "string",
  "structure": {}
}

```

Represents the source code of a weave.ly application (i.e. the component graph)

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|The graph's unique id|
|ownerId|string|false|none|(User) id of graph creator|
|structure|object|false|none|Nodes and edges of the graph (json)|

<h2 id="tocS_Sandboxes">Sandboxes</h2>
<!-- backwards compatibility -->
<a id="schemasandboxes"></a>
<a id="schema_Sandboxes"></a>
<a id="tocSsandboxes"></a>
<a id="tocssandboxes"></a>

```json
[
  {
    "id": 0,
    "sandboxId": "string",
    "graphId": "string",
    "ownerId": "string",
    "dataCreated": "string"
  }
]

```

An array of sandbox objects

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Sandbox](#schemasandbox)]|false|none|An array of sandbox objects|

<h2 id="tocS_Sandbox">Sandbox</h2>
<!-- backwards compatibility -->
<a id="schemasandbox"></a>
<a id="schema_Sandbox"></a>
<a id="tocSsandbox"></a>
<a id="tocssandbox"></a>

```json
{
  "id": 0,
  "sandboxId": "string",
  "graphId": "string",
  "ownerId": "string",
  "dataCreated": "string"
}

```

Represents a weave.ly app created through the sandbox environment

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|number|false|none|The sandboxes' unique id (internal)|
|sandboxId|string|false|none|The sandboxes' unique id, as used by external world|
|graphId|string|false|none|Id of graph source-code|
|ownerId|string|false|none|Id of user that created the sandbox|
|dataCreated|string|false|none|Timestamp upon creation|

<h2 id="tocS_ComponentState">ComponentState</h2>
<!-- backwards compatibility -->
<a id="schemacomponentstate"></a>
<a id="schema_ComponentState"></a>
<a id="tocScomponentstate"></a>
<a id="tocscomponentstate"></a>

```json
{
  "componentId": "string",
  "vals": {}
}

```

Represents the state of a deployed weave.ly component instance

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|componentId|string|false|none|Id of the component state|
|vals|object|false|none|json structure containing the actual state|

<h2 id="tocS_Measurements">Measurements</h2>
<!-- backwards compatibility -->
<a id="schemameasurements"></a>
<a id="schema_Measurements"></a>
<a id="tocSmeasurements"></a>
<a id="tocsmeasurements"></a>

```json
[
  {
    "measurementId": "string",
    "ownerId": "string",
    "userId": "string",
    "componentId": "string",
    "metadata": {},
    "data": {}
  }
]

```

An array of measurement objects

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Measurement](#schemameasurement)]|false|none|An array of measurement objects|

<h2 id="tocS_Measurement">Measurement</h2>
<!-- backwards compatibility -->
<a id="schemameasurement"></a>
<a id="schema_Measurement"></a>
<a id="tocSmeasurement"></a>
<a id="tocsmeasurement"></a>

```json
{
  "measurementId": "string",
  "ownerId": "string",
  "userId": "string",
  "componentId": "string",
  "metadata": {},
  "data": {}
}

```

Data generated by the user, either through sensors at the source of a graph or at the sink of graphs by storing through DB component

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|measurementId|string|false|none|Measurement's unique id|
|ownerId|string|false|none|id of the user that owns the graph that created the measurement|
|userId|string|false|none|id of the user that generated the data|
|componentId|string|false|none|id of the specific instance responsible for the creation of the measurement|
|metadata|object|false|none|any and all meta-data attached to the measurement|
|data|object|false|none|actual measurement data|

