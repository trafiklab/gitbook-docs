# GTFS Regional

## What does this dataset contains?

This dataset contains high quality detailled data, both static and realtime, in the GTFS format. It does not cover the entirety of Sweden.

### Data format

The data is in the GTFS format, and makes use of the GTFS Extensions. Realtime data follows the GTFS-Realtime \(GTFS-RT\) standard, and is stored in the protobuf format.

### How often is this dataset updated?

The static data in this dataset is updated on a daily basis, typically between 03:00 and 07:00.  
The realtime data \(ServiceAlerts.pb and TripUpdates.pb\) is updated every 15 seconds.  
The vehicle position data \(VehiclePositions.pb\) is updated every 3 seconds.

### Which operators are covered by this dataset?

The following table shows which operators 

| Operator | Static data | Realtime data | Vehicle positions |
| :--- | :---: | :---: | :---: |
| Dalatrafik | ✅ | ✅ | ✅ |
| KLT | ✅ | ✅ | ✅ |
| Skånetrafiken | ✅ | ✅ | ✅ |
| SL | ✅ | ✅ | ⏳ |
| UL | ✅ | ✅ | ⏳ |
| Värmlandstrafik | ✅ | 🚫 | 🚫 |
| Östgotatrafiken | ✅ | ✅ | ✅ |
| Västtrafik | ✅ | 🚫 | 🚫 |
| SJ, Tågab, Snälltåget | ✅ | 🚫 | 🚫 |

### How often does the data format changes? Do breaking changes happen?

This dataset has the **beta** status. This means that the fields can be added, or changed without prior warning. However, when breaking changes are made, you will get one or two months time to update your implementations.

