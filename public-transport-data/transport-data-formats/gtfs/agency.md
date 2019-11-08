# Agency

{% hint style="info" %}
This content was retrieved from [https://developers.google.com/transit/gtfs/reference](https://developers.google.com/transit/gtfs/reference), and has been adapted to show which fields are used by Trafiklab.
{% endhint %}

### agency.txt <a id="agencytxt"></a>

File: **Required**

Defines one or more transit agencies that have services represented in the dataset.

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
      <td style="text-align:left"><code>agency_id</code>
      </td>
      <td style="text-align:left">ID</td>
      <td style="text-align:left">Conditionally required</td>
      <td style="text-align:left">
        <p>Identifies a transit brand, which is often the same as a transit agency.
          Note that in some cases, such as when a single agency operates multiple
          separate services, agencies and brands are distinct. This document uses
          the term &quot;agency&quot; in place of &quot;brand.&quot;</p>
        <p>A transit feed can represent data from more than one agency. This field
          is required for transit feeds that contain data for multiple agencies.
          Otherwise, it&apos;s optional.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>agency_name</code>
      </td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Contains the full name of the transit agency.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>agency_url</code>
      </td>
      <td style="text-align:left">URL</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Contains the URL of the transit agency.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>agency_timezone</code>
      </td>
      <td style="text-align:left">Timezone</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Contains the timezone where the transit agency is located. If multiple
        agencies are specified in the feed, each must have the same <code>agency_timezone</code>.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>agency_lang</code>
      </td>
      <td style="text-align:left">Language code</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Specifies the primary language used by this transit agency. This setting
        helps GTFS consumers choose capitalization rules and other language-specific
        settings for the dataset.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>agency_phone</code>
      </td>
      <td style="text-align:left">Phone number</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Provides a voice telephone number for the specified agency. This field
        is a string value that presents the telephone number in a format typical
        for the agency&apos;s service area. It can and should contain punctuation
        marks to group the digits of the number. Dialable text, such as TriMet&apos;s <code>503-238-RIDE</code>,
        is permitted, but the field must not contain any other descriptive text.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>agency_fare_url</code>
      </td>
      <td style="text-align:left">URL</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Specifies the URL of a web page where a rider can purchase tickets or
        other fare instruments for the agency online.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>agency_email</code>
      </td>
      <td style="text-align:left">Email</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Contains a valid email address that&apos;s actively monitored by the agency&apos;s
        customer service department. This email address needs to be a direct contact
        point where transit riders can reach a customer service representative
        at the agency.</td>
    </tr>
  </tbody>
</table>###  <a id="stopstxt"></a>

