# ResRobot Timetables

{% hint style="info" %}
For technical details about HTTP headers, URLs,  and response structures, please use the OpenAPI Specification available on our developer portal.
{% endhint %}

## What does this API provide?

ResRobot Timetables provides a list of departures or arrivals at a given stop. Users can specify the stop, date, time, transport modes, ... . Realtime data is available for SL, Skånetrafiken, Västtrafik and Trafikverket \(All train traffic including SJ, MTRX, .... \).

### Data format

The data is formatted as JSON or XML, depending on the `format` query parameter.

### How often is this data updated?

The static data used for this API is updated when changes are made, at most once per day. Realtime data is updated once every minute.

### Which operators are covered by this dataset?

All operators which operate in Sweden are covered by the ResRobot APIs.

### How often does the data format changes? Do breaking changes happen?

This dataset has the **stable** status. This means that we will communicate when fields are added, or changed. When breaking changes are made, you will get three months or more to update your implementations.

## Using ResRobot Timetables

ResRobot Timetables consists of two different endpoints, one for departures and one for arrivals. Both endpoints take exactly the same parameters and have the same response structure. API Calls take the stop id as a parameter, as well as some other parameters to fine-tune the results. It returns a list of departures or arrivals from the given stop, including a bit of information about each vehicle, such as where it is heading or where it comes from. 



