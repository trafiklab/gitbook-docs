# Feed info

{% hint style="info" %}
This content was retrieved from [https://developers.google.com/transit/gtfs/reference](https://developers.google.com/transit/gtfs/reference), and has been adapted to show which fields are used by Trafiklab.
{% endhint %}

### feed\_info.txt <a id="feed_infotxt"></a>

File: **Optional**

The `feed_info.txt` file contains information about the feed itself, rather than the services that the feed describes. GTFS has an [`agency.txt`]() file to provide information about the agencies that operate the services described by the feed. However, the publisher of the feed is sometimes a different entity than any of the agencies, such as in the case of regional aggregators. In addition, there are some fields that are really feed-wide settings, rather than agency-wide.

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
      <td style="text-align:left"><code>feed_publisher_name</code>
      </td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Contains the full name of the organization that publishes the dataset.
        This can be the same as one of the <code>agency_name</code> values in <a href><code>agency.txt</code></a>.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>feed_publisher_url</code>
      </td>
      <td style="text-align:left">URL</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Contains the URL of the dataset publishing organization&apos;s website.
        This can be the same as one of the <code>agency_url</code> values in <a href><code>agency.txt</code></a>.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>feed_lang</code>
      </td>
      <td style="text-align:left">Language code</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Specifies the default language used for the text in this dataset. This
        setting helps GTFS consumers choose capitalization rules and other language-specific
        settings for the feed.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>feed_start_date</code>
      </td>
      <td style="text-align:left">Date</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>The dataset provides complete and reliable schedule information for service
          in the period from the beginning of the <code>feed_start_date</code> day
          to the end of the <code>feed_end_date</code> day.</p>
        <p>If both <code>feed_end_date</code> and <code>feed_start_date</code> are given,
          the end date must not precede the start date. Dataset providers are encouraged
          to give schedule data outside this period to advise passengers of likely
          future service, but dataset consumers should be mindful of its non-authoritative
          status.</p>
        <p>If <a href><code>calendar.txt</code></a> and <a href><code>calendar_dates.txt</code></a> omit
          any active calendar dates that are included within the timeframe defined
          by <code>feed_start_date</code> and <code>feed_end_date</code>, this is an
          explicit statement that there&apos;s no service on those omitted days.
          That is, <code>calendar.txt</code> and <code>calendar_dates.txt</code> are
          assumed to be an exhaustive list of the dates when service is provided.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>feed_end_date</code>
      </td>
      <td style="text-align:left">Date</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">For details on this field, see <code>feed_start_date</code> above.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>feed_version</code>
      </td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Specifies a string that indicates the current version of the GTFS dataset.
        GTFS-consuming applications can display this value to help dataset publishers
        determine whether the latest version of their dataset has been incorporated.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>feed_contact_email</code>
      </td>
      <td style="text-align:left">Email</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Provides an email address for communication about the GTFS dataset and
        data publishing practices. The <code>feed_contact_email</code> field provides
        a technical contact for GTFS-consuming applications. To provide customer
        service contact information, use the fields in <a href><code>agency.txt</code></a>.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>feed_contact_url</code>
      </td>
      <td style="text-align:left">URL</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Provides a URL for contact information, a web form, support desk, or other
        tool for communication about the GTFS dataset and data publishing practices.
        The <code>feed_contact_url</code> field provides a technical contact for
        GTFS-consuming applications. To provide customer service contact information,
        use the fields in <a href><code>agency.txt</code></a>.</td>
    </tr>
  </tbody>
</table>