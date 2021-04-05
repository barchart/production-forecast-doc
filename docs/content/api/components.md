# Components

## Responses 

### Success :id=responsessuccess
> Success

**Content Type**: <code>application/json</code>

**Response Type:** <code><code>Object</code></code>

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |
| code | <code>Integer</code> | false | false |  |

**Example**:

```json
{
  "message": "Success.",
  "code": 200
}
```

* * *

### Unauthorized :id=responsesunauthorized
> The unauthorized access.

**Content Type**: <code>application/json</code>

**Response Type:** <code><code>Object</code></code>

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |

**Example**:

```json
{
  "message": "API key is missing or not valid."
}
```

* * *

### BadRequest :id=responsesbadrequest
> The request was invalid, please see the message for more information.

**Content Type**: <code>application/json</code>

**Response Type:** <code><code>Object</code></code>

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |
| code | <code>Integer</code> | false | false |  |

**Example**:

```json
{
  "message": "No active bids available for the requested location(s) at this time.",
  "code": 204
}
```

* * *

### ServerError :id=responsesservererror
> Something is not working correctly, please contact support.

**Content Type**: <code>application/json</code>

**Response Type:** <code><code>Object</code></code>

| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| message | <code>String</code> | false | false |  |
| code | <code>Integer</code> | false | false |  |

**Example**:

```json
{
  "message": "Something is not working correctly, please contact support.",
  "code": 500
}
```

* * *

## Schemas 

### GetCropFeaturesResponse :id=schemasgetcropfeaturesresponse
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| results | [<code>Array&lt;CropFeaturesByLocation&gt;</code>](#schemasCropFeaturesByLocation) |  | false | Value of feature geotiff image returned as array. |

**Example**:

```json
{
  "results": [
    {
      "values": [
        [
          0,
          0,
          0,
          "...",
          0
        ],
        [
          0,
          0,
          0,
          "...",
          0
        ]
      ],
      "state": "IA",
      "district": "10",
      "county": "Guthrie County",
      "polygon": {},
      "start_date": "20180401",
      "end_date": "20201015",
      "mean": 0.5,
      "maximum": 1,
      "minimum": -1
    }
  ]
}
```

* * *

### GetCropClassificationResponse :id=schemasgetcropclassificationresponse
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| results | [<code>Array&lt;CropClassificationByLocation&gt;</code>](#schemasCropClassificationByLocation) |  | false | Value of crop classification geotiff image returned as array. |

**Example**:

```json
{
  "results": [
    {
      "values": [
        [
          1,
          1,
          1,
          "...",
          1
        ],
        [
          5,
          5,
          5,
          "...",
          5
        ]
      ],
      "state": "IA",
      "district": "10",
      "county": "Guthrie County",
      "polygon": {},
      "year": "20180401"
    }
  ]
}
```

* * *

### GetPolygon :id=schemasgetpolygon
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| coordinates | [<code>Array&lt;Polygon&gt;</code>](#schemasPolygon) |  | false | the internal auto-increment numeric id for the cash bid. |

**Example**:

```json
{
  "coordinates": [
    {
      "coordinates": [
        [
          -121.1958,
          37.6683
        ],
        [
          -121.1779,
          37.6687
        ],
        [
          -121.1773,
          37.6792
        ],
        [
          -121.1958,
          37.6792
        ],
        [
          -121.1958,
          37.6683
        ]
      ]
    }
  ]
}
```

* * *

### Polygon :id=schemaspolygon
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| coordinates | <code>Array</code> |  | false | array of points consist of x,y |

**Example**:

```json
{
  "coordinates": [
    [
      -121.1958,
      37.6683
    ],
    [
      -121.1779,
      37.6687
    ],
    [
      -121.1773,
      37.6792
    ],
    [
      -121.1958,
      37.6792
    ],
    [
      -121.1958,
      37.6683
    ]
  ]
}
```

* * *

### CropFeaturesByLocation :id=schemascropfeaturesbylocation
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| values | <code>Array</code> |  | false | The value of feature geotiff images of requested region. Each value is corresponding to each pixel of the geo-spatial image. |
| state | <code>String</code> | false | true | 2-char abbreviation of the state where the api request. |
| district | <code>String</code> | false | true | 2-char district code of a certain state. |
| county | <code>String</code> | false | true | The name of the county containing the applicable cash bid. |
| polygon | <code>Object</code> | false | true | The series of longitude and latitude pairs defined by user. |
| start_date | <code>String</code> | false | false | The start date of requested geo-spatial image. |
| end_date | <code>String</code> | false | false | The end date of requested geo-spatial image. |
| mean | <code>Number</code> | false | true | The mean value of feature among the requested region of each time period. |
| maximum | <code>Number</code> | false | true | The maximum value of feature among the requested region of each time period. |
| minimum | <code>Number</code> | false | true | The minimum value of feature among the requested region of each time period. |

**Example**:

```json
{
  "values": [
    [
      0,
      0,
      0,
      "...",
      0
    ],
    [
      0,
      0,
      0,
      "...",
      0
    ]
  ],
  "state": "IA",
  "district": "10",
  "county": "Guthrie County",
  "polygon": {},
  "start_date": "20180401",
  "end_date": "20201015",
  "mean": 0.5,
  "maximum": 1,
  "minimum": -1
}
```

* * *

### CropClassificationByLocation :id=schemascropclassificationbylocation
**Type**: <code>Object</code>
    
| Name | Type | Required | Nullable | Description |
| ---- | ---- | -------- | -------- | ----------- |
| values | <code>Array</code> |  | false | The value of crop classification geotiff images of requested region. Each value is corresponding to each pixel of the geo-spatial image. |
| state | <code>String</code> | false | true | 2-char abbreviation of the state where the api request. |
| district | <code>String</code> | false | true | 2-char district code of a certain state. |
| county | <code>String</code> | false | true | The name of the county containing the applicable cash bid. |
| polygon | <code>Object</code> | false | true | The series of longitude and latitude pairs defined by user. |
| year | <code>String</code> | false | false | The year of requested crop classification geo-spatial image. |

**Example**:

```json
{
  "values": [
    [
      1,
      1,
      1,
      "...",
      1
    ],
    [
      5,
      5,
      5,
      "...",
      5
    ]
  ],
  "state": "IA",
  "district": "10",
  "county": "Guthrie County",
  "polygon": {},
  "year": "20180401"
}
```

* * *

## Security 

### JWT :id=securityjwt

>The JWT authorization

**Type**: http bearer
    
#### Headers
| Name | Format | Example |
| ---- | ------ | ------- |
| Authorization | JWT | Authorization: Bearer <code>&lt;Token&gt;</code> |

* * *

