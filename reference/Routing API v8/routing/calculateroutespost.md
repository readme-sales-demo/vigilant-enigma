---
title: Calculate routes via POST
excerpt: >
  Calculates a route using a generic vehicle/pedestrian mode, e.g. car, truck,
  pedestrian, etc...


  At the moment, only selected parameters are permitted in the POST body,

  particularly those that may be restricted in the query string due to request
  size limitations.

  See the request body section below for details. All other parameters must be
  provided in the query string.

  If a parameter is provided in both the query string and the POST body, their
  values are merged.


  Post body size limit is 10MiB.
api:
  file: router_api.yaml
  operationId: calculateRoutesPost
hidden: false
---