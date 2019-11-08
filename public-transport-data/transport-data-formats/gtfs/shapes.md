# Shapes

### shapes.txt <a id="shapestxt"></a>

File: **Optional**

Shapes describe the physical path that a vehicle takes, and they're defined in the file `shapes.txt`. Shapes are associated with individual trips, and they consist of a sequence of points. Trace the points in order to follow the path of the vehicle. The points don't need to match stop locations.

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
      <td style="text-align:left"><code>shape_id</code>
      </td>
      <td style="text-align:left">ID</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Identifies a shape.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>shape_pt_lat</code>
      </td>
      <td style="text-align:left">Latitude</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Associates a shape point&apos;s latitude with a shape ID. Each row in <code>shapes.txt</code> represents
        a shape point used to define the shape.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>shape_pt_lon</code>
      </td>
      <td style="text-align:left">Longitude</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">Associates a shape point&apos;s longitude with a shape ID. Each row in <code>shapes.txt</code> represents
        a shape point used to define the shape.</td>
    </tr>
    <tr>
      <td style="text-align:left"><code>shape_pt_sequence</code>
      </td>
      <td style="text-align:left">Non-negative integer</td>
      <td style="text-align:left">Required</td>
      <td style="text-align:left">
        <p>Associates the latitude and longitude of a shape point with its sequence
          order along the shape. The values for <code>shape_pt_sequence</code> must
          increase throughout the trip but don&apos;t need to be consecutive.</p>
        <p>For example, if the shape &quot;A_shp&quot; has three points in its definition,
          the <code>shapes.txt</code> file might contain the following rows to define
          the shape:</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><code>shape_dist_traveled</code>
      </td>
      <td style="text-align:left">Non-negative float</td>
      <td style="text-align:left">Optional</td>
      <td style="text-align:left">
        <p>Provides the actual distance traveled along the shape from the first shape
          point to the point specified in this record. This information allows the
          trip planner to determine how much of the shape to draw when they show
          part of a trip on the map. The values used for <code>shape_dist_traveled</code> must
          increase along with <code>shape_pt_sequence</code>: they can&apos;t be used
          to show reverse travel along a route.</p>
        <p>The units used for <code>shape_dist_traveled</code> in the <code>shapes.txt</code> file
          must match the units that are used for this field in the <a href><code>stop_times.txt</code></a> file.</p>
        <p>For example, if a bus travels along three points defined for the shape
          &quot;A_shp,&quot; the additional <code>shape_dist_traveled</code> values,
          shown here in kilometers, would look like the following:</p>
      </td>
    </tr>
  </tbody>
</table>