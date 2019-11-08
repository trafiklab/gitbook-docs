# Stops

{% hint style="info" %}
This content was retrieved from [https://developers.google.com/transit/gtfs/reference](https://developers.google.com/transit/gtfs/reference), and has been adapted to show which fields are used by Trafiklab.
{% endhint %}

### stops.txt <a id="stopstxt"></a>

File: **Required**

Defines stops where vehicles pick up or drop off riders. Also defines stations and station entrances.

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
      <td style="text-align:left"><code>stop_id</code>
      </td>
      <td style="text-align:left">ID</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Identifies a stop, station, or station entrance. The term &quot;station
        entrance&quot; refers to both station entrances and station exits. Stops,
        stations, and station entrances are collectively referred to as locations.
        Multiple routes can use the same stop.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>stop_code</code>
      </td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Contains some short text or a number that uniquely identifies the stop
          for riders. Stop codes are often used in phone-based transit information
          systems or printed on stop signage to make it easier for riders to get
          information for a particular stop.</p>
        <p>The <code>stop_code</code> can be the same as <code>stop_id</code> if the
          ID is public facing. Leave this field blank for stops without a code presented
          to riders.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>stop_name</code>
      </td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Conditionally required</td>
      <td style="text-align:left">
        <p>Contains the name of a location. Use a name that people understand in
          the local and tourist vernacular.</p>
        <p>When the location is a boarding area, with <code>location_type=4</code>,
          include the name of the boarding area as displayed by the agency in the <code>stop_name</code>.
          It can be just one letter or text like &quot;Wheelchair boarding area&quot;
          or &quot;Head of short trains.&quot;</p>
        <p>This field is required for locations that are stops, stations, or entrances/exits,
          which have <code>location_type</code> fields of <code>0</code>, <code>1</code>,
          and <code>2</code> respectively.</p>
        <p>This field is optional for locations that are generic nodes or boarding
          areas, which have <code>location_type</code> fields of <code>3</code> and <code>4</code> respectively.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>stop_desc</code>
      </td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Describes a location. Provide useful, quality information. Don&apos;t
        simply duplicate the name of the location.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>stop_lat</code>
      </td>
      <td style="text-align:left">Latitude</td>
      <td style="text-align:left">Conditionally required</td>
      <td style="text-align:left">
        <p>Contains the latitude of a stop, station, or station entrance.</p>
        <p>This field is required for locations that are stops, stations, or entrances/exits,
          which have <code>location_type</code> fields of <code>0</code>, <code>1</code>,
          and <code>2</code> respectively.</p>
        <p>This field is optional for locations that are generic nodes or boarding
          areas, which have <code>location_type</code> fields of <code>3</code> and <code>4</code> respectively.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>stop_lon</code>
      </td>
      <td style="text-align:left">Longitude</td>
      <td style="text-align:left">Conditionally required</td>
      <td style="text-align:left">
        <p>Contains the longitude of a stop, station, or station entrance.</p>
        <p>This field is required for locations that are stops, stations, or entrances/exits,
          which have <code>location_type</code> fields of <code>0</code>, <code>1</code>,
          and <code>2</code> respectively.</p>
        <p>This field is optional for locations that are generic nodes or boarding
          areas, which have <code>location_type</code> fields of <code>3</code> and <code>4</code> respectively.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>zone_id</code>
      </td>
      <td style="text-align:left">ID</td>
      <td style="text-align:left">Conditionally required</td>
      <td style="text-align:left">Defines the fare zone for a stop. This field is required if you want to
        provide fare information with <a href><code>fare_rules.txt</code></a>. If
        this record represents a station or station entrance, the <code>zone_id</code> is
        ignored.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>stop_url</code>
      </td>
      <td style="text-align:left">URL</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Contains the URL of a web page about a particular stop. Make this different
        from the <code>agency_url</code> and <code>route_url</code> fields.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>location_type</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Defines the type of the location. The <code>location_type</code> field can
          have the following values:</p>
        <ul>
          <li><code>0</code> or (empty): Stop (or &quot;Platform&quot;). A location where
            passengers board or disembark from a transit vehicle. Stops are called
            a &quot;platform&quot; when they&apos;re defined within a <code>parent_station</code>.</li>
          <li><code>1</code>: Station. A physical structure or area that contains one
            or more platforms.</li>
          <li><code>2</code>: Station entrance or exit. A location where passengers
            can enter or exit a station from the street. The stop entry must also specify
            a <code>parent_station</code> value that references the <code>stop_id</code> of
            the parent station for the entrance. If an entrance/exit belongs to multiple
            stations, it&apos;s linked by pathways to both, and the data provider can
            either pick one station as parent, or put no parent station at all.</li>
          <li><code>3</code>: Generic node. A location within a station that doesn&apos;t
            match any other <code>location_type</code>. Generic nodes are used to link
            together the pathways defined in <a href><code>pathways.txt</code></a>.</li>
          <li><code>4</code>: Boarding area. A specific location on a platform where
            passengers can board or exit vehicles.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>parent_station</code>
      </td>
      <td style="text-align:left">ID that references <a href><code>stops.stop_id</code></a>
      </td>
      <td style="text-align:left">Conditionally required</td>
      <td style="text-align:left">
        <p>For stops that are physically located inside stations, the <code>parent_station</code> field
          identifies the station associated with the stop. Based on a combination
          of values for the <code>parent_station</code> and <code>location_type</code> fields,
          we define three types of stops:</p>
        <ul>
          <li>A parent stop is an (often large) station or terminal building that can
            contain child stops.
            <ul>
              <li>This entry&apos;s location type is <code>1</code>.</li>
              <li>The <code>parent_station</code> field contains a blank value, because parent
                stops can&apos;t contain other parent stops.</li>
            </ul>
          </li>
          <li>A child stop is located inside of a parent stop. It can be an entrance,
            platform, node, or other pathway, as defined in <a href><code>pathways.txt</code></a>.
            <ul>
              <li>This entry&apos;s <code>location_type</code> is <code>0</code> or (empty).</li>
              <li>The <code>parent_station</code> field contains the stop ID of the station
                where this stop is located.</li>
              <li>The stop referenced in <code>parent_station</code> must have <code>location_type=1</code>.</li>
            </ul>
          </li>
          <li>A standalone stop is located outside of a parent stop.
            <ul>
              <li>This entry&apos;s location type is <code>0</code> or (empty).</li>
              <li>The <code>parent_station</code> field contains a blank value, because the <code>parent_station</code> field
                doesn&apos;t apply to this stop.</li>
            </ul>
          </li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>stop_timezone</code>
      </td>
      <td style="text-align:left">Timezone</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Contains the timezone of this location. If omitted, it&apos;s assumed
          that the stop is located in the timezone specified by the <code>agency_timezone</code> in
          <a
          href><code>agency.txt</code>
            </a>.</p>
        <p>When a stop has a parent station, the stop has the timezone specified
          by the parent station&apos;s <code>stop_timezone</code> value. If the parent
          has no <code>stop_timezone</code> value, the stops that belong to that station
          are assumed to be in the timezone specified by <code>agency_timezone</code>,
          even if the stops have their own <code>stop_timezone</code> values.</p>
        <p>In other words, if a given stop has a <code>parent_station</code> value,
          any <code>stop_timezone</code> value specified for that stop must be ignored.
          Even if <code>stop_timezone</code> values are provided in <code>stops.txt</code>,
          continue to specify the times in <a href><code>stop_times.txt</code></a> relative
          to the timezone specified by the <code>agency_timezone</code> field in <code>agency.txt</code>.
          This ensures that the time values in a trip always increase over the course
          of a trip, regardless of which timezones the trip crosses.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>wheelchair_boarding</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Identifies whether wheelchair boardings are possible from the specified
          stop, station, or station entrance. This field can have the following values:</p>
        <ul>
          <li><code>0</code> or (empty): Indicates that there&apos;s no accessibility
            information available for this stop.</li>
          <li><code>1</code>: Indicates that at least some vehicles at this stop can
            be boarded by a rider in a wheelchair.</li>
          <li><code>2</code>: Indicates that wheelchair boarding isn&apos;t possible
            at this stop.</li>
        </ul>
        <p>When a stop is part of a larger station complex, as indicated by the presence
          of a <code>parent_station</code> value, the stop&apos;s <code>wheelchair_boarding</code> field
          has the following additional semantics:</p>
        <ul>
          <li><code>0</code> or (empty): The stop inherits its <code>wheelchair_boarding</code> value
            from the parent station if it exists.</li>
          <li><code>1</code>: Some accessible path exists from outside the station to
            the specific stop or platform.</li>
          <li><code>2</code>: There are no accessible paths from outside the station
            to the specific stop or platform.</li>
        </ul>
        <p>For station entrances/exits, the <code>wheelchair_boarding</code> field
          has the following additional semantics:</p>
        <ul>
          <li><code>0</code> or (empty): The station entrance inherits its <code>wheelchair_boarding</code> value
            from the parent station if it exists.</li>
          <li><code>1</code>: The station entrance is wheelchair accessible, such as
            when an elevator is available to reach platforms that aren&apos;t at-grade.</li>
          <li><code>2</code>: There are no accessible paths from the entrance to the
            station platforms.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>level_id</code>
      </td>
      <td style="text-align:left">ID that references <a href><code>levels.level_id</code></a>
      </td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Provides the level of the location. The same level can be used by multiple
        unlinked stations.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>platform_code</code>
      </td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Provides the platform identifier for a platform stop, which is a stop
        that belongs to a station. Just include the platform identifier, such as <code>G</code> or <code>3</code>.
        Don&apos;t include words like &quot;platform&quot; or &quot;track&quot;
        or the feed&apos;s language-specific equivalent. This allows feed consumers
        to more easily internationalize and localize the platform identifier into
        other languages.</td>
    </tr>
  </tbody>
</table>###  <a id="routestxt"></a>

