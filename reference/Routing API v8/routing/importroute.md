---
title: Calculate a route from a sequence of trace points
excerpt: >
  Creates a route from a sequence of trace points.


  Post body size limit is 10MiB.


  For best results, use 1Hz GPS data or any points that have a spacing of a few
  meters between them.

  For traces with less frequent points, the Route Import service will attempt to
  create an approximate reconstruction.

  In some situations, when consecutive points are too far apart (more than about
  30 kilometers of on-road distance), they could be considered unreachable and
  one of them could fail to be matched.
api:
  file: router_api.yaml
  operationId: importRoute
hidden: false
---