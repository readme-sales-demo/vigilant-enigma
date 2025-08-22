---
title: Get route by handle via POST
excerpt: >
  Decodes and returns a route from a previously calculated route handle.


  **Disclaimer: A route handle is not suitable for persistent route storage! It
  can be

  invalidated at any time.**


  A route handle encodes a previously calculated route. A route can be decoded
  from a handle

  as long as the service uses the same map data and encoding that were used when
  retrieving the handle.


  Thus it is suitable for caching routes compactly. It can be used to retrieve
  updated traffic

  information or other data along the route. However, a user should be prepared
  to recalculate

  the route when decoding the handle fails.


  All parameters of the `/routes` endpoint are supported, except for
  `destination`, `via`,

  `alternatives` and `routingMode`. See also the `return` parameter of `/routes`
  endpoint.


  The `origin` parameter can be provided to update the start of the previously
  calculated

  route.


  The `transportMode` parameter does not have to match the transport mode
  previously used for

  route calculation. However, when using a different transport mode, the request
  may fail,

  e.g. when the route has road segments forbidden for the provided transport
  mode.


  Only selected parameters are permitted in the POST body. See the request body
  section below for details.

  If a parameter is provided in both the query string and the POST body, their
  values are merged.


  Post body size limit is 10MiB.


  Please refer to the Developer Guide for more information and examples.
api:
  file: router_api.yaml
  operationId: getRoutesByHandlePost
hidden: false
---