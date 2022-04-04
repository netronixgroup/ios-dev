Implement a single page application which reads measurements from stream (EventSource). The changes should be reflected as soon as they are updated. 

Measurements can be one of following types "string", "float" or array with coordinates (Location).

The visualization can be in a form of a simple table, but feel free to use other options.

You are free to choose any library you need (for communication, visualisation, util) to finish the task, as long as you use some dependency manager  (CocoaPods, VendorKit etc.)

#### Requirements:

* Use Objective C and/or Swift 
* Implement at least one test
* Track your development in github
* Use github readme.md to write documentation for building and testing the application

#### API Description

The API consists of one event source, accessible at http://wsdemo.envdev.io/sse. The stream is pushing data as array of timeseries with metadata and measurements. A timeserie is key-value map of structure:

- _id uniquely identifies the timeserie
- _name_, e.g. Pressure, Temperature, Serial
- _unit_, e.g. V, mg/m³
- _measurements_ is an array of timestamp (uniq epoch) and value tuples

Example:
```
[
  {
    "name":"Pressure",
    "unit":"hPa",
    "measurements":[
    ],
    "_id":"58c15afe518ca70001b80345"
  },
  {
    "name":"PM1",
    "unit":"mg/m³",
    "measurements":[
      [
        1489066748,
        0.35888445412371583
      ],
      [
        1489066749,
        0.38890237784380327
      ],
      [
        1489066750,
        0.36088984314940226
      ]
    ],
    "_id":"58c15afe518ca70001b80340"
  },
  {
    "name":"Location",
    "measurements":[
      [
        1489066746,
        [
          40.55404852193788,
          -73.27629907400552
        ]
      ],
    "_id":"58c15afe518ca70001b80343"
  }
]
```
