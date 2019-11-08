# Transfers

{% hint style="info" %}
This content was retrieved from [https://developers.google.com/transit/gtfs/reference](https://developers.google.com/transit/gtfs/reference), and has been adapted to show which fields are used by Trafiklab.
{% endhint %}

### transfers.txt <a id="transferstxt"></a>

File: **Optional**

When an itinerary is calculated, GTFS-consuming applications interpolate transfers based on allowable time and stop proximity. The `transfers.txt` file specifies additional rules and overrides for selected transfers.

<table>
  <thead>
    <tr>
      <th style="text-align:left">Field name</th>
      <th style="text-align:left">Type</th>
      <th style="text-align:left">Required</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><code>from_stop_id</code>
      </td>
      <td style="text-align:left">ID that references <a href><code>stops.stop_id</code></a>
      </td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Identifies a stop or station where a connection between routes begins.
        If this field refers to a station, the transfer rule applies to all of
        its child stops.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>to_stop_id</code>
      </td>
      <td style="text-align:left">ID that references <a href><code>stops.stop_id</code></a>
      </td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Identifies a stop or station where a connection between routes ends. If
        this field refers to a station, the transfer rule applies to all of its
        child stops.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>transfer_type</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">
        <p>Indicates the type of connection for the specified pair (<code>from_stop_id</code>, <code>to_stop_id</code>).
          The following are valid values for this field:</p>
        <ul>
          <li><code>0</code> or (empty): This is a recommended transfer point between
            routes.</li>
          <li><code>1</code>: This is a timed transfer point between two routes. The
            departing vehicle is expected to wait for the arriving one, with sufficient
            time for a rider to transfer between routes.</li>
          <li><code>2</code>: This transfer requires a minimum amount of time between
            arrival and departure to ensure a connection. The time required to transfer
            is specified by <code>min_transfer_time</code>.</li>
          <li><code>3</code>: Transfers aren&apos;t possible between routes at this
            location.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>min_transfer_time</code>
      </td>
      <td style="text-align:left">Non-negative integer</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Defines the amount of time, in seconds, that must be available in an itinerary
        to permit a transfer between routes at the specified stops. The <code>min_transfer_time</code> must
        be sufficient to permit a typical rider to move between the two stops,
        as well as some buffer time to allow for schedule variance on each route.</td>
    </tr>
  </tbody>
</table>