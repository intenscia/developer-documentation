## Sessions

The Sessions resource allows the buyer to monitor survey performance in real time.  Buyers will have access to the number of entrants, breakdown of Fulcrum and client statuses, cost of completes, supplier EPC, system conversion, and median LOI.  Additionally, buyers will be able to bucket these data points by supplier and/or by date.  

#### Sessions Model

| Property                     | Type     | Description                                                                                |
|------------------------------|----------|--------------------------------------------------------------------------------------------|
| fulcrumStatus                | int      | Response code associated with the respondent's Fulcrum session.                            |
| clientStatus                 | int      | Response code associated with the respondent's client survey attempt.                      |
| entryDate                    | datetime | Date and time the respondent entered Fulcrum.                                              |
| lastDate                     | datetime | Date and time the respondent last interacted with the session.                             |
| supplierID                   | int      | ID associated with the supplier account where the respondent was sourced.                  |
| PID                          | string   | A supplier's unique respondent identifier.                                                 |
| RID                          | string   | Unique session ID per study per respondent.                                                |

#### Statistics Model

| Property                     | Type     | Description                                                                                       |
|------------------------------|----------|---------------------------------------------------------------------------------------------------|
| EPC                          | float    | The earnings a supplier can expect per entrant on average (Earnings Per Click).                   |
| totalEntrants                | int      | Total number of survey entrants to Fulcrum.                                                       |
| medianLOI                    | int      | Median time for a respondent to complete the survey excluding the Fulcrum prescreener in minutes. |
| cost                         | float    | Total cost of the survey in USD.                                                                  |
| systemConversion             | float    | Total number of completes divided by total number of entrants.                                    |
| fulcrumStatus                | json     | Total count of each Fulcrum Response Code.                                                        |
| clientStatus                 | json     | Total count of each Client Response Code.                                                         |

### GET List Sessions

Returns a list of all sessions associated with a given survey for a buyer to analyze respondent-level data.

> Definition

```plaintext
GET https://api.samplicio.us/demand/v2-beta/sessions
```

> Example Request

```shell
curl -H "Authorization: YOUR_API_KEY_HERE" https://api.samplicio.us/demand/v2-beta/sessions?survey-number={survey-number}&entry-date-after={entry-date-after}&entry-date-before={entry-date-before}
```

```ruby
require 'net/http'

uri = URI('https://api.samplicio.us/demand/v2-beta/sessions?survey-number={survey-number}&entry-date-after={entry-date-after}&entry-date-before={entry-date-before}')

http = Net::HTTP.new(uri.host, uri.port)

http.use_ssl = true

request = Net::HTTP::Get.new(uri.request_uri)

request['Authorization'] = YOUR_API_KEY_HERE

response = http.request(request)
```

```php
<?php
$URL = "https://api.samplicio.us/demand/v2-beta/sessions?survey-number={survey-number}&entry-date-after={entry-date-after}&entry-date-before={entry-date-before}";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Authorization: YOUR_API_KEY_HERE";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);
?>
```

```python
import requests

url = 'https://api.samplicio.us/demand/v2-beta/sessions?survey-number={survey-number}&entry-date-after={entry-date-after}&entry-date-before={entry-date-before}'

headers = {'Authorization' : YOUR_API_KEY_HERE}

response = requests.get(url, headers=headers)
```

```csharp
using System.Net;

WebRequest request = WebRequest.Create("https://api.samplicio.us/demand/v2-beta/sessions?survey-number={survey-number}&entry-date-after={entry-date-after}&entry-date-before={entry-date-before}");

request.Headers.Add("Authorization", YOUR_API_KEY_HERE);

WebResponse response = request.GetResponse();
```

```javascript
const https = require('https');

var options = {
  "method": "GET",
  "hostname": "https://api.samplicio.us",
  "path": "/demand/v2-beta/sessions?survey-number={survey-number}&entry-date-after={entry-date-after}&entry-date-before={entry-date-before}",
  "headers": {'Authorization': YOUR_API_KEY_HERE}
};

var request = https.request(options, function (response) {
  var chunks = [];

  response.on("data", function (chunk) {
    chunks.push(chunk);
  });

});

request.end();
```

> Example Response

```json
{
  "sessions": [
    {
      "fulcrumStatus": 41,
      "entryDate": "2017-06-09T17:58:20Z",
      "lastDate": "2017-06-09T17:58:22Z",
      "supplierID": 1,
      "PID": "XXXXX-XXXX",
      "RID": "XXXXX-XXXX",
      "clientStatus": -1
    },
    {
      "fulcrumStatus": 3,
      "entryDate": "2017-06-09T17:58:39Z",
      "lastDate": "2017-06-09T17:58:46Z",
      "supplierID": 1,
      "PID": "XXXXX-XXXX",
      "RID": "XXXXX-XXXX",
      "clientStatus": 10
    }
  ]
}
```

#### Query Arguments

| Argument                     | Type     | Required  | Description                                                                    |
|------------------------------|----------|-----------|--------------------------------------------------------------------------------|
| survey-number          | int      | true      | Unique number associated with the survey.                                            |
| entry-date-after            | datetime | false     | Lower bound entryDate.                                                               |
| entry-date-before           | datetime | false     | Upper bound entryDate.                                                               |
| supplier-id            | int      | false     | ID associated with the supplier account.                                             |

### GET Aggregate Statistics

> Definition

Returns statistics for a buyer to analyze survey-level data. Data can be segmented by supplier.

```plaintext
GET https://api.samplicio.us/demand/v2-beta/sessions/statistics
```

> Example Request

```shell
curl -H "Authorization: YOUR_API_KEY_HERE" https://api.samplicio.us/demand/v2-beta/sessions/statistics?survey-number={survey-number}&entry-date-after={entry-date-after}&entry-date-before={entry-date-before}&group-by={group-by}
```

```ruby
require 'net/http'

uri = URI('https://api.samplicio.us/demand/v2-beta/sessions/statistics?survey-number={survey-number}&entry-date-after={entry-date-after}&entry-date-before={entry-date-before}&group-by={group-by}')

http = Net::HTTP.new(uri.host, uri.port)

http.use_ssl = true

request = Net::HTTP::Get.new(uri.request_uri)

request['Authorization'] = YOUR_API_KEY_HERE

response = http.request(request)
```

```php
<?php
$URL = "https://api.samplicio.us/demand/v2-beta/sessions/statistics?survey-number={survey-number}&entry-date-after={entry-date-after}&entry-date-before={entry-date-before}&group-by={group-by}";

$aHTTP['http']['method']  = 'GET';

$aHTTP['http']['header']  = "Authorization: YOUR_API_KEY_HERE";

$context = stream_context_create($aHTTP);

$response = file_get_contents($URL, false, $context);
?>
```

```python
import requests

url = 'https://api.samplicio.us/demand/v2-beta/sessions/statistics?survey-number={survey-number}&entry-date-after={entry-date-after}&entry-date-before={entry-date-before}&group-by={group-by}'

headers = {'Authorization' : YOUR_API_KEY_HERE}

response = requests.get(url, headers=headers)
```

```csharp
using System.Net;

WebRequest request = WebRequest.Create("https://api.samplicio.us/demand/v2-beta/sessions/statistics?survey-number={survey-number}&entry-date-after={entry-date-after}&entry-date-before={entry-date-before}&group-by={group-by}");

request.Headers.Add("Authorization", YOUR_API_KEY_HERE);

WebResponse response = request.GetResponse();
```

```javascript
const https = require('https');

var options = {
  "method": "GET",
  "hostname": "https://api.samplicio.us",
  "path": "/demand/v2-beta/sessions/statistics?survey-number={survey-number}&entry-date-after={entry-date-after}&entry-date-before={entry-date-before}&group-by={group-by}",
  "headers": {'Authorization': YOUR_API_KEY_HERE}
};

var request = https.request(options, function (response) {
  var chunks = [];

  response.on("data", function (chunk) {
    chunks.push(chunk);
  });

});

request.end();
```

> Example Response

```json
{
  "groups": [
    {
    "groupInfo": {
        "field": "supplierID",
        "value": 1
      },
      "statistics": {
        "clientStatus": {
          "1": 89,
          "10": 29,
          "20": 150,
          "40": 125,
          "-1": 53
        },
        "EPC": 0.26,
        "totalEntrants": 446,
        "medianLOI": 26,
        "cost": 117,
        "fulcrumStatus": {
          "1": 3,
          "3": 393,
          "23": 2,
          "30": 3,
          "31": 1,
          "36": 4,
          "38": 5,
          "41": 6,
          "138": 16,
          "230": 11,
          "-1": 2
        },
        "systemConversion": 0.07
      }
    }
  ]
}
```

#### Query Arguments

| Argument                     | Type     | Required  | Description                                                                    |
|------------------------------|----------|-----------|--------------------------------------------------------------------------------|
| survey-number                | int      | true      | Unique number associated with the survey.                                      |
| entry-date-after                  | datetime | false     | Lower bound entryDate.                                                         |
| entry-date-before                 | datetime | false     | Upper bound entryDate.                                                         |
| supplier-id                  | int      | false     | ID associated with the supplier account.                                       |
| group-by                     | string   | false     | Desired grouping of statistics (options: `supplier, month, day, hour`).                          |

The group-by argument can group the statistics by multiple groups, for example grouping by month and then day would be `group-by=month,supplier`.