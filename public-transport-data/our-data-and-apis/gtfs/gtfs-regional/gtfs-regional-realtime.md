# Realtime data

## Retrieving realtime data

Read the specifications at dev.trafiklab.se for technical details. In order to retrieve the static data you need an API key. Follow the link below to read more about API keys.

{% page-ref page="../../../../an-introduction-to-trafiklab/using-trafiklab/getting-api-keys.md" %}

## Available realtime data

### ServiceAlerts

Service alerts allow you to get information about disruptions on the transit network. This can anything from planned roadworks \(a certain stop might not get served for a few days\) to electricity outages on a rail network. ServiceAlerts are broad and general information. Delays and cancellations of individual trips are usually communicated using [Trip updates](gtfs-regional-realtime.md#tripupdates). See[ the table on the GTFS Regional overview page](./#which-operators-are-covered-by-this-dataset) to find out which operators are supported \(Realtime data column\).

{% hint style="info" %}
ServiceAlerts can remain unchanged for relatively long periods \(for example a couple of hours\). You can prevent unnecessary downloads by making use of [Conditional HTTP requests](../../../transport-data-formats/json/conditional-get-requests.md).
{% endhint %}

### TripUpdates

Trip updates contain realtime departure and arrival times for individual trips. This means you can get the current, estimated delay for each vehicle on each stop. See[ the table on the GTFS Regional overview page](./#which-operators-are-covered-by-this-dataset) to find out which operators are supported \(Realtime data column\).

{% hint style="warning" %}
In some cases it isn't possible to link certain delays to a specific trip. In this case, they may be linked to a route instead.
{% endhint %}

### VehiclePositions

The vehiclepositions.pb feed contains the GPS positions for all operators. Depending on the operator, these positions are updated every 1 to 3 seconds. The availability of this data is indicated in a separate column in [ the GTFS Regional availability table](./#which-operators-are-covered-by-this-dataset). 

## Using realtime data

You can read more about how to use realtime data in our Using data chapter:

{% page-ref page="../../../transport-data-formats/using-gtfs-files/" %}



