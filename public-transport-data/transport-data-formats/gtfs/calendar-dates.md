# Calendar dates

{% hint style="info" %}
This content was retrieved from [https://developers.google.com/transit/gtfs/reference](https://developers.google.com/transit/gtfs/reference), and has been adapted to show which fields are used by Trafiklab.
{% endhint %}

### calendar\_dates.txt <a id="calendar_datestxt"></a>

File: **Conditionally required**

The `calendar_dates` file allows you to explicitly activate or disable service by date. You can use it in two ways:

* **Recommended**: Use `calendar_dates.txt` to create any exceptions to the default service categories defined in the [`calendar.txt`]() file. This is a good approach if your service is generally regular with just a few changes on explicit dates, such as a school scedule or to accommodate special event services. In this case, `calendar_dates.service_id` is an ID that references `calendar.service_id`.
* **Alternate**: Omit [`calendar.txt`](), and include every date of service in `calendar_dates.txt`. If your schedule varies most days of the month, or you want to programmatically output service dates without the need to specify a normal weekly schedule, this approach might be preferable. In this case, `service_id` is an ID.

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
      <td style="text-align:left">ID that references <a href><code>calendar.service_id</code></a>, or ID</td>
      <td
      style="text-align:left">Required</td>
        <td style="text-align:left">
          <p>Identifies a set of dates when a service exception is available for one
            or more routes. Each pair of (<code>service_id</code>, <code>date</code>)
            can only appear once in <code>calendar_dates.txt</code>.</p>
          <p>If the same <code>service_id</code> value appears in both the <a href><code>calendar.txt</code></a> and <code>calendar_dates.txt</code> files,
            the information in <code>calendar_dates.txt</code> modifies the service information
            specified in <code>calendar.txt</code>.</p>
          <p>This field is referenced by the <a href><code>trips.txt</code></a> file.</p>
        </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>date</code>
      </td>
      <td style="text-align:left">Date</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Specifies a particular date when service availability is different than
        normal. You can use the <code>exception_type</code> field to indicate whether
        service is available on the specified date.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>exception_type</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">
        <p>Indicates whether service is available on the date specified in the <code>date</code> field.
          The following are valid values for this field:</p>
        <ul>
          <li><code>1</code>: Service has been added for the specified date.</li>
          <li><code>2</code>: Service has been removed for the specified date.</li>
        </ul>
        <p>For example, suppose a route has one set of trips available on holidays
          and another set of trips available on all other days. You could have one <code>service_id</code> that
          corresponds to the regular service schedule and another <code>service_id</code> that
          corresponds to the holiday schedule. For a particular holiday, you would
          use the <code>calendar_dates.txt</code> file to add the holiday to the holiday <code>service_id</code> and
          to remove the holiday from the regular <code>service_id</code> schedule.</p>
      </td>
    </tr>
  </tbody>
</table>