# Trips

{% hint style="info" %}
This content was retrieved from [https://developers.google.com/transit/gtfs/reference](https://developers.google.com/transit/gtfs/reference), and has been adapted to show which fields are used by Trafiklab.
{% endhint %}

### trips.txt <a id="tripstxt"></a>

File: **Required**

Defines trips for each route. A trip is a sequence of two or more stops that occur during a specific time period.

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
      <td style="text-align:left"><code>route_id</code>
      </td>
      <td style="text-align:left">ID that references <a href><code>routes.route_id</code></a>
      </td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Identifies a route.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>service_id</code>
      </td>
      <td style="text-align:left">ID that references <a href><code>calendar.service_id</code></a> or <a href><code>calendar_dates.service_id</code></a>
      </td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Identifies a set of dates when service is available for one or more routes.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>trip_id</code>
      </td>
      <td style="text-align:left">ID</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Identifies a trip.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>trip_headsign</code>
      </td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Contains the text that appears on signage that identifies the trip&apos;s
          destination to riders. Use this field to distinguish between different
          patterns of service on the same route.</p>
        <p>If the headsign changes during a trip, you can override the <code>trip_headsign</code> with
          values from the <code>stop_headsign</code> field in <a href><code>stop_times.txt</code></a>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>trip_short_name</code>
      </td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Contains the public-facing text that&apos;s shown to riders to identify
          the trip, such as the train numbers for commuter rail trips. If riders
          don&apos;t commonly rely on trip names, leave this field blank.</p>
        <p>If a <code>trip_short_name</code> is provided, it needs to uniquely identify
          a trip within a service day. Don&apos;t use it for destination names or
          limited/express designations.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>direction_id</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Indicates the direction of travel for a trip. Use this field to distinguish
          between bi-directional trips with the same <code>route_id</code>. The following
          are valid values for this field:</p>
        <ul>
          <li><code>0</code>: Travel in one direction of your choice, such as outbound
            travel.</li>
          <li><code>1</code>: Travel in the opposite direction, such as inbound travel.</li>
        </ul>
        <p>This field isn&apos;t used in routing, but instead provides a way to separate
          trips by direction when you publish time tables. You can specify names
          for each direction with the <code>trip_headsign</code> field.</p>
        <p>For example, for a set of trips you could use the <code>trip_headsign</code> and <code>direction_id</code> fields
          together to assign names for travel in each direction. A <a href><code>trips.txt</code></a> file
          could contain the following rows for use in its time tables:</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>block_id</code>
      </td>
      <td style="text-align:left">ID</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Identifies the block to which the trip belongs. A block consists of a
        single trip or many sequential trips made with the same vehicle. The trips
        are grouped into a block by the use of a shared service day and <code>block_id</code>.
        A <code>block_id</code> can include trips with different service days, which
        then makes distinct blocks. For more details, see <a href>Blocks and service days example</a>.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>shape_id</code>
      </td>
      <td style="text-align:left">ID that references <a href><code>shapes.shape_id</code></a>
      </td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Defines a geospatial shape that describes the vehicle travel for a trip.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>wheelchair_accessible</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Identifies whether wheelchair boardings are possible for the specified
          trip. This field can have the following values:</p>
        <ul>
          <li><code>0</code> or (empty): There&apos;s no accessibility information available
            for this trip.</li>
          <li><code>1</code>: The vehicle used on this particular trip can accommodate
            at least one rider in a wheelchair.</li>
          <li><code>2</code>: No riders in wheelchairs can be accommodated on this trip.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>bikes_allowed</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Identifies whether bicycles are allowed on the specified trip. This field
          can have the following values:</p>
        <ul>
          <li><code>0</code> or (empty): There&apos;s no bike information available for
            the trip.</li>
          <li><code>1</code>: The vehicle used on this particular trip can accommodate
            at least one bicycle.</li>
          <li><code>2</code>: No bicycles are allowed on this trip.</li>
        </ul>
      </td>
    </tr>
  </tbody>
</table>#### Blocks and service day example <a id="example-showing-blocks-and-service-day"></a>

The following table shows how to create trips for a single vehicle, where those trips fall into distinct blocks for every day of the week. The stop times correspond to the earliest `arrival_time` and the latest `departure_time` for the block, as given in [`stop_times.txt`]().

| route\_id | trip\_id | service\_id | block\_id | First stop time | Last stop time |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `red` | `trip_1` | `mon-tues-wed-thurs-fri-sat-sun` | `red_loop` | 22:00:00 | 22:55:00 |
| `red` | `trip_2` | `fri-sat-sun` | `red_loop` | 23:00:00 | 23:55:00 |
| `red` | `trip_3` | `fri-sat` | `red_loop` | 24:00:00 | 24:55:00 |
| `red` | `trip_4` | `mon-tues-wed-thurs` | `red_loop` | 20:00:00 | 20:50:00 |
| `red` | `trip_5` | `mon-tues-wed-thurs` | `red_loop` | 21:00:00 | 21:50:00 |

The following notes describe two of the blocks defined by the table above:

* On Friday evening into Saturday morning, a single vehicle operates `trip_1`, `trip_2`, and `trip_3`, from 10:00 PM through 12:55 AM. The last trip occurs on Saturday, from 12:00 AM to 12:55 AM, but it's defined as part of the Friday "service day" because the times are 24:00:00 to 24:55:00.
* On Monday, Tuesday, Wednesday, and Thursday, a single vehicle operates `trip_1`, `trip_4`, and `trip_5` in a block from 8:00 PM to 10:55 PM.

