# Routes

{% hint style="info" %}
This content was retrieved from [https://developers.google.com/transit/gtfs/reference](https://developers.google.com/transit/gtfs/reference), and has been adapted to show which fields are used by Trafiklab.
{% endhint %}

### routes.txt <a id="routestxt"></a>

File: **Required**

Defines transit routes. A route is a group of trips that are displayed to riders as a single service.

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
      <td style="text-align:left">ID</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Identifies a route.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>agency_id</code>
      </td>
      <td style="text-align:left">ID that references <a href><code>agency.agency_id</code></a>
      </td>
      <td style="text-align:left">Conditionally required</td>
      <td style="text-align:left">Defines an agency for the specified route. This field is required when
        the dataset provides data for routes from more than one agency in <a href><code>agency.txt</code></a>.
        Otherwise, it&apos;s optional.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>route_short_name</code>
      </td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Conditionally required</td>
      <td style="text-align:left">
        <p>Contains the short name of a route. This is a short, abstract identifier
          like <code>32</code>, <code>100X</code>, or <code>Green</code> that riders
          use to identify a route, but which doesn&apos;t give any indication of
          what places the route serves.</p>
        <p>At least one of <code>route_short_name</code> or <code>route_long_name</code> must
          be specified, or both if appropriate. If the route has no short name, specify
          a <code>route_long_name</code> and use an empty string as the value for this
          field.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>route_long_name</code>
      </td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Conditionally required</td>
      <td style="text-align:left">
        <p>Contains the full name of a route. This name is generally more descriptive
          than the name from <code>route_short_name</code> and often includes the route&apos;s
          destination or stop.</p>
        <p>At least one of <code>route_short_name</code> or <code>route_long_name</code> must
          be specified, or both if appropriate. If the route has no long name, specify
          a <code>route_short_name</code> and use an empty string as the value for
          this field.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>route_desc</code>
      </td>
      <td style="text-align:left">Text</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Describes a route. Be sure to provide useful, quality information for
          this field. Don&apos;t simply duplicate the name of the route.</p>
        <p>For example: <code>&quot;A&quot; trains operate between Inwood-207 St, Manhattan and Far Rockaway-Mott Ave, Queens at all times. From about 6 AM until about midnight, additional &quot;A&quot; trains operate between Inwood-207 St and Lefferts Blvd (trains typically alternate between Lefferts Blvd and Far Rockaway).</code>
        </p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>route_type</code>
      </td>
      <td style="text-align:left">Enum</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">
        <p>Describes the type of transportation used on a route. The following are
          valid values for this field:</p>
        <ul>
          <li><code>0</code>: Tram, streetcar, or light rail. Used for any light rail
            or street-level system within a metropolitan area.</li>
          <li><code>1</code>: Subway or metro. Used for any underground rail system
            within a metropolitan area.</li>
          <li><code>2</code>: Rail. Used for intercity or long-distance travel.</li>
          <li><code>3</code>: Bus. Used for short- and long-distance bus routes.</li>
          <li><code>4</code>: Ferry. Used for short- and long-distance boat service.</li>
          <li><code>5</code>: Cable car. Used for street-level cable cars where the
            cable runs beneath the car.</li>
          <li><code>6</code>: Gondola or suspended cable car. Typically used for aerial
            cable cars where the car is suspended from the cable.</li>
          <li><code>7</code>: Funicular. Used for any rail system that moves on steep
            inclines with a cable traction system.</li>
        </ul>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>route_url</code>
      </td>
      <td style="text-align:left">URL</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Contains the URL of a web page for a particular route. This URL needs
        to be different from the <code>agency_url</code> value.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>route_color</code>
      </td>
      <td style="text-align:left">Color</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>In systems that assigns colors to routes, the <code>route_color</code> field
          defines a color that corresponds to a route. If no color is specified,
          the default route color is white, <code>FFFFFF</code>.</p>
        <p>The color difference between <code>route_color</code> and <code>route_text_color</code> needs
          to provide sufficient contrast when viewed on a black and white screen.
          The <a href="https://www.w3.org/TR/AERT#color-contrast">W3C techniques for accessibility evaluation and repair tools</a> document
          offers a useful algorithm to evaluate color contrast. There are also helpful
          online tools to help you choose contrasting colors, such as the <a href="http://snook.ca/technical/colour_contrast/colour.html#fg=33FF33,bg=333333">snook.ca Color Contrast Check application</a>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>route_text_color</code>
      </td>
      <td style="text-align:left">Color</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Specifies a legible color for text that&apos;s drawn against the background
          color of <code>route_color</code>. If no color is specified, the default
          text color is black, <code>000000</code>.</p>
        <p>The color difference between <code>route_color</code> and <code>route_text_color</code> needs
          to provide sufficient contrast when viewed on a black and white screen.
          The <a href="https://www.w3.org/TR/AERT#color-contrast">W3C techniques for accessibility evaluation and repair tools</a> document
          offers a useful algorithm to evaluate color contrast. There are also helpful
          online tools to help you choose contrasting colors, such as the <a href="http://snook.ca/technical/colour_contrast/colour.html#fg=33FF33,bg=333333">snook.ca Color Contrast Check application</a>.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>route_sort_order</code>
      </td>
      <td style="text-align:left">Non-negative integer</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">Specifies the order in which to present the routes to customers. Routes
        with smaller <code>route_sort_order</code> values need to be displayed before
        routes with larger <code>route_sort_order</code> values.</td>
    </tr>
  </tbody>
</table>###  <a id="tripstxt"></a>

