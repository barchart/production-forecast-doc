# Quick Start Guide

## Get an API key

If you'd like to use our service, please [visit our website](https://www.barchart.com/cmdty/contact) and fill out the form.  You can also send us an email at cmdty@barchart.com.  It's worth nothing that the more information you can provide us in the request will allow us to deliver a solution which best fits your needs.  Some information that would be helpful would include:
* Use Case - What are you looking to do with the information?
* Data Access - Is your application public or only available to subscribers?  Can users download the data?
* Historical Data - Do you require historical information or only current prices?
* Access Type - Do you want to see data for a zip code or for a collection of bids that you specify?

Once we have an understanding of what you're looking to do our team will be able to get you started.

## Make your first query

Let's retrieve NDVI data for your county:
* Open any browser you have
* Put your API key and Zip Code into the url template -  http://ondemand.websol.barchart.com/getCropFeatures.json?apikey={YOUR_API_KEY}&featureType=NDVI&locationType=county&state={Your_State}&fipsCode={Your_County_Fipscode}&start_date=20201001&end_date=20201031 -, then copy it
* Past the url into the browser, and hit enter
* Voila! Should qualified data return to your browser, similar to below:
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

## Explore more

Congrats! You've made your first query. Now, you can check detailed API documentation at API Reference Section, and explore more advanced methods to query grain production forecats in API Examples Section
