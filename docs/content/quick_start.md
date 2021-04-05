## 01 Get an API key

GO to [cmdty website](https://www.barchart.com/cmdty/contact) and fill out the `Get Started` form.
Barchart team will set-up an API Key for you.

## 02 Make your first query

Let's retrieve NDVI data for your county:
* Open any browser you have
* Put your API key and Zip Code into the url template -  http://ondemand.websol.barchart.com/getCropFeatures.json?apikey={YOUR_API_KEY}&featureType=NDVI&locationType=county&state={Your_State}&fipsCode={Your_County_Fipscode}&start_date=20201001&end_date=20201031 -, then copy it
* Past the url into the browser, and hit enter
* Voila! Should qualified grain bids return to your browser, similar to below:
```
"status": {
    "code": 200,
    "message": "Success."
    },
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
      "start_date": "20201001",
      "end_date": "20201008",
      "mean": 0.5,
      "maximum": 1,
      "minimum": -1
    },
    ...,
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
      "start_date": "20201025",
      "end_date": "20201030",
      "mean": 0.5,
      "maximum": 1,
      "minimum": -1
    },

  ]
}
```

## 03 Explore more

Congrats! You've made your first query. Now, you can check detailed API documentation at API Reference Section, and explore more advanced methods to query grain prices data in API Examples Section