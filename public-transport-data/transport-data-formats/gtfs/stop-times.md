# Stop times

{% hint style="info" %}
This content was retrieved from [https://developers.google.com/transit/gtfs/reference](https://developers.google.com/transit/gtfs/reference), and has been adapted to show which fields are used by Trafiklab.
{% endhint %}

### stop\_times.txt <a id="stop_timestxt"></a>

File: **Required**

Provides the times when a vehicle arrives at and departs from individual stops for each trip.

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
      <td style="text-align:left"><code>trip_id</code>
      </td>
      <td style="text-align:left">ID that references <a href><code>trips.trip_id</code></a>
      </td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Identifies a trip.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>arrival_time</code>
      </td>
      <td style="text-align:left">Time</td>
      <td style="text-align:left">Conditionally required</td>
      <td style="text-align:left">
        <p>Specifies the arrival time at a specific stop for a specific trip on a
          route. An arrival time must be specified for the first and the last stop
          in a trip.</p>
        <p>If you don&apos;t have separate times for arrival and departure at a stop,
          enter the same value for <code>arrival_time</code> and <code>departure_time</code>.</p>
        <p>For information on how to enter arrival times for stops where the vehicle
          strictly adheres to a schedule, see <a href>Timepoints</a>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>departure_time</code>
      </td>
      <td style="text-align:left">Time</td>
      <td style="text-align:left">Conditionally required</td>
      <td style="text-align:left">
        <p>Specifies the departure time from a specific stop for a specific trip
          on a route. A departure time must be specified for the first and the last
          stop in a trip, even if the vehicle does not allow boarding at the last
          stop.</p>
        <p>If you don&apos;t have separate times for arrival and departure at a stop,
          enter the same value for <code>arrival_time</code> and <code>departure_time</code>.</p>
        <p>For information on how to enter departure times for stops where the vehicle
          strictly adheres to a schedule, see <a href>Timepoints</a>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>stop_id</code>
      </td>
      <td style="text-align:left">ID that references <a href><code>stops.stop_id</code></a>
      </td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">
        <p>Identifies the serviced stop. Multiple routes can use the same stop.</p>
        <p>If <code>location_type</code> is used in <code>stops.txt</code>, all stops
          referenced in <a href><code>stop_times.txt</code></a> must have <code>location_type=0</code>.
          Where possible, <code>stop_id</code> values should remain consistent between
          feed updates. In other words, stop A with <code>stop_id=1</code> should have <code>stop_id=1</code> in
          all subsequent data updates. If a stop isn&apos;t a timepoint, enter blank
          values for <code>arrival_time</code> and <code>departure_time</code>. For
          more details, see <a href>Timepoints</a>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>stop_sequence</code>
      </td>
      <td style="text-align:left">Non-negative integer</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">
        <p>Identifies the order of the stops for a particular trip. The values for <code>stop_sequence</code> must
          increase throughout the trip but do not need to be consecutive.</p>
        <p>For example, the first stop on the trip could have a <code>stop_sequence</code> of <code>1</code>,
          the second stop on the trip could have a <code>stop_sequence</code> of <code>23</code>,
          the third stop could have a <code>stop_sequence</code> of <code>40</code>,
          and so on.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>stop_headsign</code>
      </td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Contains the text, as shown on signage, that identifies the trip&apos;s
        destination to riders. Use this field to override the default <code>trip_headsign</code> when
        the headsign changes between stops. If this headsign is associated with
        an entire trip, use <code>trip_headsign</code> instead.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>pickup_type</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Indicates whether riders are picked up at a stop as part of the normal
          schedule or whether a pickup at the stop isn&apos;t available. This field
          also allows the transit agency to indicate that riders must call the agency
          or notify the driver to arrange a pickup at a particular stop. The following
          are valid values for this field:</p>
        <ul>
          <li><code>0</code> or (empty): Regularly scheduled pickup</li>
          <li><code>1</code>: No pickup available</li>
          <li><code>2</code>: Must phone agency to arrange pickup</li>
          <li><code>3</code>: Must coordinate with driver to arrange pickup</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>drop_off_type</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Indicates whether riders are dropped off at a stop as part of the normal
          schedule or whether a dropoff at the stop is unavailable. This field also
          allows the transit agency to indicate that riders must call the agency
          or notify the driver to arrange a dropoff at a particular stop. The following
          are valid values for this field:</p>
        <ul>
          <li><code>0</code> or (empty): Regularly scheduled drop off</li>
          <li><code>1</code>: No dropoff available</li>
          <li><code>2</code>: Must phone agency to arrange dropoff</li>
          <li><code>3</code>: Must coordinate with driver to arrange dropoff</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>shape_dist_traveled</code>
      </td>
      <td style="text-align:left">Non-negative float</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>When used in the <a href><code>stop_times.txt</code></a> file, the <code>shape_dist_traveled</code> field
          positions a stop as a distance from the first shape point. The <code>shape_dist_traveled</code> field
          represents a real distance traveled along the route in units such as feet
          or kilometers.</p>
        <p>For example, if a bus travels a distance of 5.25 kilometers from the start
          of the shape to the stop, the <code>shape_dist_traveled</code> for the stop
          ID would be entered as <code>5.25</code>. This information allows the trip
          planner to determine how much of the shape to draw when they show part
          of a trip on the map.</p>
        <p>The values used for <code>shape_dist_traveled</code> must increase along
          with <code>stop_sequence</code>: they can&apos;t be used to show reverse
          travel along a route. The units used for <code>shape_dist_traveled</code> in
          the <code>stop_times.txt</code> file must match the units that are used for
          this field in the <a href><code>shapes.txt</code></a> file.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>timepoint</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Indicates if the specified arrival and departure times for a stop are
          strictly adhered to by the transit vehicle, or if they&apos;re instead
          approximate or interpolated times. This field allows a GTFS producer to
          provide interpolated stop times that potentially incorporate local knowledge,
          but still indicate if the times are approximate.</p>
        <p>For stop-time entries with specified arrival and departure times, the
          following are valid values for this field:</p>
        <ul>
          <li><code>0</code>: Times are considered approximate.</li>
          <li><code>1</code> or (empty): Times are considered exact.</li>
        </ul>
        <p>For stop-time entries without specified arrival and departure times, feed
          consumers must interpolate arrival and departure times. Feed producers
          can optionally indicate that such an entry is not a timepoint (with <code>timepoint=0</code>),
          but it&apos;s an error to mark an entry as a timepoint (with <code>timepoint=1</code>)
          without specifying arrival and departure times.</p>
      </td>
    </tr>
  </tbody>
</table>#### Timepoints <a id="timepoints"></a>

Timepoints are scheduled stops where the vehicle strictly adheres to the specified arrival and departure times. For example, if a transit vehicle arrives at a stop before the scheduled departure time, it holds until the departure time.

If a given stop isn't a timepoint, use either an empty string value for the `arrival_time` or `departure_time` fields or provide an interpolated time. To indicate that interpolated times have been provided, use a value of `0` for the `timepoint` field. If that's done, you must use a value of `timepoint=1` to indicate times entered as timepoints.

Be sure to provide arrival and departure times for all stops that are timepoints.

