# Calendar

{% hint style="info" %}
This content was retrieved from [https://developers.google.com/transit/gtfs/reference](https://developers.google.com/transit/gtfs/reference), and has been adapted to show which fields are used by Trafiklab.
{% endhint %}

### calendar.txt <a id="calendartxt"></a>

File: **Conditionally required**

Defines service dates when service is available for particular routes. Uses a weekly schedule. This file specifies start and end dates, as well as the days of the week when service is available. This file is required unless all of the dates of service are defined in [`calendar_dates.txt`]().

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
      <td style="text-align:left"><code>service_id</code>
      </td>
      <td style="text-align:left">ID</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Uniquely identifies a set of dates when service is available for one or
        more routes. Each <code>service_id</code> value can appear at most once in
        a <code>calendar.txt</code> file. This value is referenced by the <a href><code>trips.txt</code></a> file.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>monday</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">
        <p>Indicates whether the service is valid for all Mondays within the date
          range specified by the <code>start_date</code> and <code>end_date</code> fields.
          The following are valid values for this field:</p>
        <ul>
          <li><code>1</code>: Service is available for all Mondays in the date range.</li>
          <li><code>0</code>: Service isn&apos;t available for Mondays in the date range.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>tuesday</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Functions similarly to the <code>monday</code> field, except for Tuesdays.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>wednesday</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Functions similarly to the <code>monday</code> field, except for Wednesdays.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>thursday</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Functions similarly to the <code>monday</code> field, except for Thursdays.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>friday</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Functions similarly to the <code>monday</code> field, except for Fridays.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>saturday</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Functions similarly to the <code>monday</code> field, except for Saturdays.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>sunday</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Functions similarly to the <code>monday</code> field, except for Sundays.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>start_date</code>
      </td>
      <td style="text-align:left">Date</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Contains the start date for the service.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>end_date</code>
      </td>
      <td style="text-align:left">Date</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Contains the end date for the service. This date is included in the service
        interval.</td>
    </tr>
  </tbody>
</table>###  <a id="calendar_datestxt"></a>

