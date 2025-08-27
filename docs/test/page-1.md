---
title: Page 1
deprecated: false
hidden: false
metadata:
  robots: index
---

This section shows how to quickly get started with HERE Routing API v8 on the [HERE platform](https://platform.here.com).

> #### Note
>
> This section provides information on the minimum setup required to quickly begin using the HERE Routing API. For more detailed information on HERE account setup, app registration, and authentication, see the [Identity and Access Management Developer Guide](https://www.here.com/docs/bundle/identity-and-access-management-developer-guide/page/README.html).

## Get a HERE Account

You can get started with a free HERE platform account and the flexible HERE Base Plan. For more information, see the [HERE Base Plan Pricing](https://www.here.com/get-started/pricing).
If your company has already established a HERE platform organization, contact your organization admin who can invite you to join your company's organization.

## Get an API key

To get an API key, follow these steps:

1. Sign in to the HERE platform.
2. Select the **Access Manager** from the launcher.
3. Select the **Apps** tab and click **Register new app**.
4. Enter a name for the app and add an optional description.
5. Click **Register**. The HERE platform creates a new app with a unique app ID.
6. On the **Credentials** tab, select **API Keys**, and then click **Create API key**. You can generate two API keys for every app.

## Send a request

To get started, send a `GET` request to calculate a route between two locations.
A basic request must contain the following parameters:

* `origin`, which contains the WGS 84 coordinates of the starting point of the route.
* `destination`, which contains the WGS 84 coordinates of the target point of the route.
* `transportMode`, which defines the mode of transportation for which a route is calculated.

Send the following request to calculate a route for a car.
Note the included `return=summary` parameter which adds a summary of the time required to travel the route and its length to the response.
Remember to replace `YOUR_API_KEY` with the API key created for your app.

```bash
curl -gX GET 'https://router.hereapi.com/v8/routes?'\
'transportMode=car&'\
'origin=52.5308,13.3847&'\
'destination=52.5264,13.3686&'\
'return=summary&'\
'apiKey=YOUR_API_KEY'
```

### Response

If the route calculation is successful, the response contains the calculated route with departure and arrival times in one or more [sections](concepts/section.md).
Additional summary information, such as the length and duration are also provided.

```json
{
  "routes": [
    {
      "id": "cc0441f1-b8ca-4410-95d5-bfd930053c03",
      "sections": [
        {
          "id": "256fef6e-6712-47fe-8e68-095c1204eb1a",
          "type": "vehicle",
          "departure": {
            "place": {
              "type": "place",
              "location": {
                "lat": 52.5309837,
                "lng": 13.384567
              },
              "originalLocation": {
                "lat": 52.5307999,
                "lng": 13.3847
              }
            }
          },
          "arrival": {
            "place": {
              "type": "place",
              "location": {
                "lat": 52.5263761,
                "lng": 13.3686186
              },
              "originalLocation": {
                "lat": 52.5263999,
                "lng": 13.3686
              }
            }
          },
          "summary": {
            "duration": 243,
            "length": 1206,
            "baseDuration": 136
          },
          "transport": {
            "mode": "car"
          }
        }
      ]
    }
  ]
}
```

## Next steps

* See [Transport modes overview](./concepts/transport-modes.md) to learn about calculating routes for specific transport types.
* See [Waypoints overview](./concepts/waypoint.md) to learn about waypoints - locations on the map that allow you to shape the route to your needs.
* See [Vehicle properties](tutorials/route-with-vehicle-parameters.md) to learn how to include the physical properties of the vehicle in the request and how that affects route calculation.

What’s Next
Tell your users what they should do after they've finished this page

AI Agent
Save to Branch
Save
