# ResRobot Station lookup

{% hint style="info" %}
For technical details about HTTP headers, URLs,  and response structures, please use the OpenAPI Specification available on our developer portal.
{% endhint %}

## What does this API provide?

GTFS Sverige is our national feed. It contains all public transport in the entire country of Sweden. The data is correct, but lacks the details which are included in the GTFS Regional dataset.

### Data format

The data is formatted as JSON or XML, depending on the `format` query parameter.

### How often is this data updated?

The static data used for this API is updated when changes are made, at most once per day.

### Which operators are covered by this dataset?

All operators which operate in Sweden are covered by the ResRobot APIs.

### How often does the data format changes? Do breaking changes happen?

This dataset has the **stable** status. This means that we will communicate when fields are added, or changed. When breaking changes are made, you will get three months or more to update your implementations.

## Using ResRobot Station lookup

ResRobot Station lookup takes the search string and the wanted number of results as parameters, and returns a list of matching stations with their location, name and id. Users can choose between exact matching and approximate matching by adding a question mark to the end of the search string. 

{% hint style="info" %}
Instead of using the station lookup endpoint, you can also use the stops.txt file from GTFS Sverige 2. This way you can provide autocomplete  and other search functions without internet access. It will make your application more responsive and more reliable as you don't have to wait for API responses. See [Combining data and APIs](../combining-data.md) for more information.
{% endhint %}



