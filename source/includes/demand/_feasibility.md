##Feasibility

### POST Show Time to Completion

> Definition

```plaintext
POST https://api.samplicio.us/Demand/v1/Feasibility/Time
```

> Example Request

```shell
curl -H "Content-Type: application/json" -H "Authorization: YOUR_API_KEY_HERE" -X POST --data '{"CountryLanguageID": 9, "LengthOfInterview": 5, "Incidence": 100,  "Price": 4.5, "Quotas": [{"CompletesPerDay": [1000], "Conditions": [{"QuestionID": 42, "PreCodes": ["18", "19", "20", "21", "22", "23", "24", "25", "26", "27", "28", "29"]}, {"QuestionID": 43, "PreCodes": ["1"] } ] }, {"CompletesPerDay": [1000], "Conditions": [{"QuestionID": 42, "PreCodes": ["18", "19", "20", "21", "22", "23", "24", "25", "26", "27", "28", "29"]}, {"QuestionID": 43, "PreCodes": ["2"] } ] }] }}' https://api.samplicio.us/Demand/v1/Feasibility/Time
```

```ruby
require 'net/http'
require 'json'

uri = URI('https://api.samplicio.us/Demand/v1/Feasibility/Time')

http = Net::HTTP.new(uri.host, uri.port)

http.use_ssl = true

fullUriPath = uri.path + '?' + uri.query

request = Net::HTTP::Post.new(fullUriPath, initheader = {'Content-Type' =>'application/json'})

request.body = {CountryLanguageID: 9, LengthOfInterview: 5, Incidence: 100,  Price: 4.5, Quotas: [{Completes: 1000, Conditions: [{QuestionID: 42, PreCodes: ["18", "19", "20", "21", "22", "23", "24",
 "25", "26", "27", "28", "29"]}, {QuestionID: 43, PreCodes: ["1"] } ] }, {Completes: 1000, Conditions: [{QuestionID: 42, PreCodes: ["18", "19", "20", "21", "22", "23", "24",
 "25", "26", "27", "28", "29"]}, {QuestionID: 43, PreCodes: ["2"] } ] }] }.to_json

request['Authorization'] = YOUR_API_KEY_HERE

response = http.request(request)

```

```php
<?php
$curl = curl_init();

$params = '{"CountryLanguageID": 9, "LengthOfInterview": 5, "Incidence": 100, "Price": 4.5, "Quotas": [{"Completes": 1000, "Conditions": [{"QuestionID": 42, "PreCodes": ["18", "19", "20", "21", "22", "23", "24",
 "25", "26", "27", "28", "29"]}, {"QuestionID": 43, "PreCodes": ["1"] } ] }, {"Completes": 1250, "Conditions": [{"QuestionID": 42, "PreCodes": ["18", "19", "20", "21", "22", "23", "24",
 "25", "26", "27", "28", "29"]}, {"QuestionID": 43, "PreCodes": ["2"] } ] } ] }';

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.samplicio.us/Demand/v1/Feasibility/Time",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_HTTPHEADER => array('Content-Type: application/json', 'Authorization: YOUR_API_KEY_HERE'),
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => $params,
));

$response = curl_exec($curl);

curl_close($curl);
?>

```

```python
import requests, json

url = 'https://api.samplicio.us/Demand/v1/Feasibility/Time'
params = {'CountryLanguageID': 9, 'LengthOfInterview': 5, 'Incidence': 100, 'Quotas': [{'CompletesPerDay': [1000], 'Conditions': [{'QuestionID': 42, 'PreCodes': ["18", "19", "20", "21", "22", "23", "24","25", "26", "27", "28", "29"]}, {'QuestionID': 43, 'PreCodes': ["1"] } ] }, {'CompletesPerDay': [1250], 'Conditions': [{'QuestionID': 42, 'PreCodes': ["18", "19", "20", "21", "22", "23", "24", "25", "26", "27", "28", "29"]}, {'QuestionID': 43, 'PreCodes': ["2"] } ] }] }

data = json.dumps(params)
headers = {'Content-type': 'application/json', 'Authorization' : 'YOUR_API_KEY_HERE', 'Accept': 'text/plain'}

response = requests.post(url, data=data, headers=headers)
```

```csharp
using System.IO;
using System.Net;

WebRequest request = WebRequest.Create("https://api.samplicio.us/Demand/v1/Feasibility/Time");

string args = @"{
                 ""CountryLanguageID"": 9,
                 ""LengthOfInterview"": 5,
                 ""Incidence"": 100,
                 ""Price"": 4.5,
                 ""Quotas"": [
                                {
                                  ""CompletesPerDay"": [1000],
                                  ""Conditions"":
                                  [
                                    {
                                      ""QuestionID"": 42,
                                      ""PreCodes"": [""18"", ""19"", ""20"", ""21"",
                                                     ""22"", ""23"", ""24"", ""25"",
                                                     ""26"", ""27"", ""28"", ""29""]
                                    },
                                    {
                                      ""QuestionID"": 43,
                                      ""PreCodes"": [""1""]
                                    }
                                  ]
                                },
                                {
                                  ""CompletesPerDay"": [1250],
                                  ""Conditions"":
                                  [
                                    {
                                      ""QuestionID"": 42,
                                      ""PreCodes"": [""18"", ""19"", ""20"", ""21"",
                                                     ""22"", ""23"", ""24"", ""25"",
                                                     ""26"", ""27"", ""28"", ""29""]
                                    },
                                    {
                                      ""QuestionID"": 43,
                                      ""PreCodes"": [""2""]
                                    }
                                  ]
                                }
                              ]
                }";

request.Method = "POST";
request.ContentType = "application/json";
request.Headers.Add("Authorization", "YOUR_API_KEY_HERE");

using(StreamWriter streamWriter = new StreamWriter(request.GetRequestStream()))
{
streamWriter.Write(args);
streamWriter.Flush();
streamWriter.Close();
}

WebResponse response = request.GetResponse();
```

```javascript
const https = require('https');

var options = {
  "method": "POST",
  "hostname": "api.samplicio.us",
  "path": "/Demand/v1/Feasibility/Time",
  "headers": {'Content-Type': 'application/json',
  'Authorization': 'YOUR_API_KEY_HERE'
  }
};

var json = {"CountryLanguageID": 9, "LengthOfInterview": 5, "Incidence": 100, "Price": 4.5, "Quotas": [{"Completes": 1000, "Conditions": [{"QuestionID": 42, "PreCodes": ["18", "19", "20", "21", "22", "23", "24",
 "25", "26", "27", "28", "29"]}, {"QuestionID": 43, "PreCodes": ["1"] } ] }, {"Completes": 1250, "Conditions": [{"QuestionID": 42, "PreCodes": ["18", "19", "20", "21", "22", "23", "24",
 "25", "26", "27", "28", "29"]}, {"QuestionID": 43, "PreCodes": ["2"] } ] }] };

var params = JSON.stringify(json);

var request = https.request(options, function (response) {
  var chunks = [];

  response.on("data", function (chunk) {
    chunks.push(chunk);
  });
});

request.write(params);

request.end();
```

> Example Response

```json
{
  "ApiResult": 0,
  "ApiResultCode": 0,
  "ApiAccount": "Anon",
  "AccountType": 1,
  "ApiAccountStatus": 1,
  "AccountCode": "AA",
  "ApiMessages": [
    "API Message: Response initialized.",
    "API Message: GetTimeForQuotas successful."
  ],
  "ResultCount": 1,
  "Quotas": [
    {
      "Completes": 1000,
      "Conditions": [
        {
          "PreCodes": [
              "18",
              "19",
              "20",
              "21",
              "22",
              "23",
              "24",
              "25",
              "26",
              "27",
              "28",
              "29"
          ],
          "QuestionID": 42
        },
        {
          "PreCodes": [
            "1"
          ],
          "QuestionID": 43
        }
      ],
      "Days": 0.4115335
    },
    {
      "Completes": 1250,
      "Conditions": [
        {
          "PreCodes": [
            "18",
            "19",
            "20",
            "21",
            "22",
            "23",
            "24",
            "25",
            "26",
            "27",
            "28",
            "29"
          ],
          "QuestionID": 42
        },
        {
          "PreCodes": [
            "2"
          ],
          "QuestionID": 43
        }
      ],
      "Days": 0.254863828
    }
  ]
}
```

Returns the estimated time in days to achieve the total number of completes specified, given the project specifications.

#### Arguments

| Property          | Type  | Required | Description                                                     |
|-------------------|-------|----------|-----------------------------------------------------------------|
| CountryLanguageID | int   | true     | Unique number associated with a specific Country-Language pair. |
| LengthofInterview | int   | true     | Expected Length of Interview, in minutes.                       |
| Incidence         | int   | true     | Expected incidence rate for the study.                          |
| Price             | double| true     | Price in USD per complete offered.                              |
| Quotas            | array | true     | Contains an array of CompletesPerDay and Conditions pairs. The conditions array can be blank for no conditions.|
| QuestionID        | int   | false    | Unique ID associated with a question.                           |
| PreCodes          | int   | false    | Precode associated with an answer for a specific questionID.    |



### POST Show Price

> Definition

```plaintext
POST https://api.samplicio.us/Demand/v1/Feasibility/Price
```

> Example Request

```shell
curl -H "Content-Type: application/json" -H "Authorization: YOUR_API_KEY_HERE" -X POST --data '{"CountryLanguageID": 9, "LengthOfInterview": 5, "Incidence": 100, "Quotas": [{"CompletesPerDay": [1000, 1500], "Conditions": [{"QuestionID": 42, "PreCodes": ["18", "19", "20", "21", "22", "23", "24", "25", "26", "27", "28", "29"]}, {"QuestionID": 43, "PreCodes": ["1"] } ] }, ] }' https://api.samplicio.us/Demand/v1/Feasibility/Price
```

```ruby
require 'net/http'
require 'json'

uri = URI('https://api.samplicio.us/Demand/v1/Feasibility/Price')

http = Net::HTTP.new(uri.host, uri.port)

http.use_ssl = true

fullUriPath = uri.path + '?' + uri.query

request = Net::HTTP::Post.new(fullUriPath, initheader = {'Content-Type' =>'application/json'})

request.body = {CountryLanguageID: 9, LengthOfInterview: 5, Incidence: 100, Quotas: [{CompletesPerDay: [1000, 1500], Conditions: [{QuestionID: 42, PreCodes: ["18", "19", "20", "21", "22", "23", "24",
 "25", "26", "27", "28", "29"]}, {QuestionID: 43, PreCodes: ["1"] } ] }, ] }.to_json

request['Authorization'] = YOUR_API_KEY_HERE

response = http.request(request)

```

```php
<?php
$curl = curl_init();

$params = '{"CountryLanguageID": 9, "LengthOfInterview": 5, "Incidence": 100, "Quotas": [{"CompletesPerDay": [1000, 1500], "Conditions": [{"QuestionID": 42, "PreCodes": ["18", "19", "20", "21", "22", "23", "24",
 "25", "26", "27", "28", "29"]}, {"QuestionID": 43, "PreCodes": ["1"] } ] }, ] }';

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.samplicio.us/Demand/v1/Feasibility/Price",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_HTTPHEADER => array('Content-Type: application/json', 'Authorization: YOUR_API_KEY_HERE'),
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => $params,
));

$response = curl_exec($curl);

curl_close($curl);
?>

```

```python
import requests, json

url = 'https://api.samplicio.us/Demand/v1/Feasibility/Price'
params = {'CountryLanguageID': 9, 'LengthOfInterview': 5, 'Incidence': 100, 'Quotas': [{'CompletesPerDay': [1000, 1500], 'Conditions': [{'QuestionID': 42, 'PreCodes': ["18", "19", "20", "21", "22", "23", "24", "25", "26", "27", "28", "29"]}, {'QuestionID': 43, 'PreCodes': ["1"] } ] }, ] }
data = json.dumps(params)
headers = {'Content-type': 'application/json', 'Authorization' : 'YOUR_API_KEY_HERE', 'Accept': 'text/plain'}

response = requests.post(url, data=data, headers=headers)
```

```csharp
using System.IO;
using System.Net;

WebRequest request = WebRequest.Create("https://api.samplicio.us/Demand/v1/Feasibility/Price");

string args = @"{
                 ""CountryLanguageID"": 9,
                 ""LengthOfInterview"": 5,
                 ""Incidence"": 100,
                 ""Quotas"": [
                                {""CompletesPerDay"": [1000, 1500],
                                  ""Conditions"":
                                  [
                                    {
                                      ""QuestionID"": 42,
                                      ""PreCodes"": [""18"", ""19"", ""20"", ""21"",
                                                     ""22"", ""23"", ""24"", ""25"",
                                                     ""26"", ""27"", ""28"", ""29""]
                                    },
                                    {
                                      ""QuestionID"": 43,
                                      ""PreCodes"": [""1""]
                                    }
                                  ]
                                },
                              ]
                }";

request.Method = "POST";
request.ContentType = "application/json";
request.Headers.Add("Authorization", "YOUR_API_KEY_HERE");

using(StreamWriter streamWriter = new StreamWriter(request.GetRequestStream()))
{
streamWriter.Write(args);
streamWriter.Flush();
streamWriter.Close();
}

WebResponse response = request.GetResponse();
```

```javascript
const https = require('https');

var options = {
  "method": "POST",
  "hostname": "api.samplicio.us",
  "path": "/Demand/v1/Feasibility/Price",
  "headers": {'Content-Type': 'application/json',
  'Authorization': 'YOUR_API_KEY_HERE'
  }
};

var json = {"CountryLanguageID": 9, "LengthOfInterview": 5, "Incidence": 100, "Quotas": [{"CompletesPerDay": [1000, 1500], "Conditions": [{"QuestionID": 42, "PreCodes": ["18", "19", "20", "21", "22", "23", "24",
 "25", "26", "27", "28", "29"]}, {"QuestionID": 43, "PreCodes": ["1"] } ] }, ] };

var params = JSON.stringify(json);

var request = https.request(options, function (response) {
  var chunks = [];

  response.on("data", function (chunk) {
    chunks.push(chunk);
  });
});

request.write(params);

request.end();
```

> Example Response

```json
{
  "ApiResult": 0,
  "ApiResultCode": 0,
  "ApiAccount": "Anon",
  "AccountType": 1,
  "ApiAccountStatus": 1,
  "AccountCode": "AA",
  "ApiMessages": [
    "API Message: Response initialized.",
    "API Message: GetPriceForQuotas successful."
  ],
  "ResultCount": 1,
  "Quotas": [
    {
      "CompletesPerDay": [
        1000,
        1500
      ],
      "Conditions": [
        {
          "PreCodes": [
            "18",
            "19",
            "20",
            "21",
            "22",
            "23",
            "24",
            "25",
            "26",
            "27",
            "28",
            "29"
          ],
          "QuestionID": 42
        },
        {
          "PreCodes": [
            "1"
          ],
          "QuestionID": 43
        }
      ],
      "Prices": [
        {
          "PercentPrice100": 1.25,
          "PercentPrice25": 0.75,
          "PercentPrice50": 1,
          "PercentPrice75": 1
        },
        {
          "PercentPrice100": 1.5,
          "PercentPrice25": 1,
          "PercentPrice50": 1,
          "PercentPrice75": 1.48
        }
      ]
    }
  ]
}
```

Returns a tiered model of price in USD per complete, given the inputs for Number of Respondents per day and qualifications. PercentPrice(N) value is the price at which N percent of the total number of completes can be achieved.

#### Arguments

| Property          | Type  | Required | Description                                                     |
|-------------------|-------|----------|-----------------------------------------------------------------|
| CountryLanguageID | int   | true     | Unique number associated with a specific Country-Language pair. |
| LengthofInterview | int   | true     | Expected Length of Interview, in minutes.                       |
| Incidence         | int   | true     | Expected incidence rate for the study.                          |
| Quotas            | array | true     | Contains arrays for CompletesPerDay and Conditions. The conditions array can be blank for no conditions.|
| QuestionID        | int   | false    | Unique ID associated with a question.                           |
| PreCodes          | int   | false    | Precode associated with an answer for a specific questionID.    |




### POST Show Completes per Day

> Definition

```plaintext
POST https://api.samplicio.us/Demand/v1/Feasibility/NumberOfRespondents
```


> Example Request

```shell
curl -H "Content-Type: application/json" -H "Authorization: YOUR_API_KEY_HERE" -X POST --data '{"CountryLanguageID": 9, "LengthOfInterview": 5, "Incidence": 100, "Price": 5, "Quotas": [{"Conditions": [{"QuestionID": 42, "PreCodes": ["18", "19", "20", "21", "22", "23", "24", "25", "26", "27", "28", "29"]}, {"QuestionID": 43, "PreCodes": ["1"] } ] }, ] }' https://api.samplicio.us/Demand/v1/Feasibility/NumberOfRespondents
```

```ruby
require 'net/http'
require 'json'

uri = URI('https://api.samplicio.us/Demand/v1/Feasibility/NumberOfRespondents')

http = Net::HTTP.new(uri.host, uri.port)

http.use_ssl = true

fullUriPath = uri.path + '?' + uri.query

request = Net::HTTP::Post.new(fullUriPath, initheader = {'Content-Type' =>'application/json'})

request.body = {CountryLanguageID: 9, LengthOfInterview: 5, Incidence: 100, Price: 5, Quotas: [{Conditions: [{QuestionID: 42, PreCodes: ["18", "19", "20", "21", "22", "23", "24", "25", "26", "27", "28", "29"]}, {QuestionID: 43, PreCodes: ["1"] } ] }, ] }.to_json

request['Authorization'] = YOUR_API_KEY_HERE

response = http.request(request)

```

```php
<?php
$curl = curl_init();

$params = '{"CountryLanguageID": 9, "LengthOfInterview": 5, "Incidence": 100, "Price": 5, "Quotas": [{"Conditions": [{"QuestionID": 42, "PreCodes": ["18", "19", "20", "21", "22", "23", "24",
 "25", "26", "27", "28", "29"]}, {"QuestionID": 43, "PreCodes": ["1"] } ] }, ] }';

curl_setopt_array($curl, array(
  CURLOPT_URL => "https://api.samplicio.us/Demand/v1/Feasibility/NumberOfRespondents",
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => "",
  CURLOPT_HTTPHEADER => array('Content-Type: application/json', 'Authorization: YOUR_API_KEY_HERE'),
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 30,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => "POST",
  CURLOPT_POSTFIELDS => $params,
));

$response = curl_exec($curl);

curl_close($curl);
?>

```

```python
import requests, json

url = 'https://api.samplicio.us/Demand/v1/Feasibility/NumberOfRespondents'
params = {'CountryLanguageID': 9, 'LengthOfInterview': 5, 'Incidence': 100, 'Price': 5, 'Quotas': [{'Conditions': [{'QuestionID': 42, 'PreCodes': ["18", "19", "20", "21", "22", "23", "24", "25", "26", "27", "28", "29"]}, {'QuestionID': 43, 'PreCodes': ["1"] } ] }, ] }
data = json.dumps(params)
headers = {'Content-type': 'application/json', 'Authorization' : 'YOUR_API_KEY_HERE', 'Accept': 'text/plain'}

response = requests.post(url, data=data, headers=headers)
```

```csharp
using System.IO;
using System.Net;

WebRequest request = WebRequest.Create("https://api.samplicio.us/Demand/v1/Feasibility/NumberOfRespondents");

string args = @"{
                 ""CountryLanguageID"": 9,
                 ""LengthOfInterview"": 5,
                 ""Incidence"": 100,
                 ""Price"": 5,
                 ""Quotas"": [
                                {""Conditions"":
                                  [
                                    {
                                      ""QuestionID"": 42,
                                      ""PreCodes"": [""18"", ""19"", ""20"", ""21"",
                                                     ""22"", ""23"", ""24"", ""25"",
                                                     ""26"", ""27"", ""28"", ""29""]
                                    },
                                    {
                                      ""QuestionID"": 43,
                                      ""PreCodes"": [""1""]
                                    }
                                  ]
                                },
                              ]
                }";

request.Method = "POST";
request.ContentType = "application/json";
request.Headers.Add("Authorization", "YOUR_API_KEY_HERE");

using(StreamWriter streamWriter = new StreamWriter(request.GetRequestStream()))
{
streamWriter.Write(args);
streamWriter.Flush();
streamWriter.Close();
}

WebResponse response = request.GetResponse();
```

```javascript
const https = require('https');

var options = {
  "method": "POST",
  "hostname": "api.samplicio.us",
  "path": "/Demand/v1/Feasibility/NumberOfRespondents",
  "headers": {'Content-Type': 'application/json',
  'Authorization': 'YOUR_API_KEY_HERE'
  }
};

var json = {"CountryLanguageID": 9, "LengthOfInterview": 5, "Incidence": 100, "Price": 5, "Quotas": [{"Conditions": [{"QuestionID": 42, "PreCodes": ["18", "19", "20", "21", "22", "23", "24",
 "25", "26", "27", "28", "29"]}, {"QuestionID": 43, "PreCodes": ["1"] } ] }, ] };

var params = JSON.stringify(json);

var request = https.request(options, function (response) {
  var chunks = [];

  response.on("data", function (chunk) {
    chunks.push(chunk);
  });
});

request.write(params);

request.end();
```

> Example Response

```json
{
  "ApiResult": 0,
  "ApiResultCode": 0,
  "ApiAccount": "Anon",
  "AccountType": 1,
  "ApiAccountStatus": 1,
  "AccountCode": "AA",
  "ApiMessages": [
    "API Message: Response initialized.",
    "API Message: GetNumberOfRespondents successful."
  ],
  "ResultCount": 1,
  "Quotas": [
    {
      "CompletesPerDay": 5294,
      "Conditions": [
        {
          "PreCodes": [
            "18",
            "19",
            "20",
            "21",
            "22",
            "23",
            "24",
            "25",
            "26",
            "27",
            "28",
            "29"
          ],
          "QuestionID": 42
        },
        {
          "PreCodes": [
            "1"
          ],
          "QuestionID": 43
        }
      ]
    }
  ]
}
```

Returns the number of completes achievable given the parameters submitted, based on the Exchange's historical performance.

#### Arguments

| Property          | Type  | Required | Description                                                        |
|-------------------|-------|----------|--------------------------------------------------------------------|
| CountryLanguageID | int   | true     | Unique number associated with a specific Country-Language pair.    |
| LengthofInterview | int   | true     | Expected Length of Interview, in minutes.                          |
| Incidence         | int   | true     | Expected incidence rate for the study.                             |
| Price             | double| true     | Price in USD per complete offered.                                 |
| Quotas            | array | true     | Contains an array of quotas, which can be blank for no conditions. |
| QuestionID        | int   | false    | Unique ID associated with a question.                              |
| PreCodes          | int   | false    | Precode associated with an answer for a specific questionID.       |
