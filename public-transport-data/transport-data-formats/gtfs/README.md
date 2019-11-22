# Reading GTFS Files

{% hint style="info" %}
This content was retrieved from [https://developers.google.com/transit/gtfs/reference](https://developers.google.com/transit/gtfs/reference), and has been adapted to show which fields are used by Trafiklab.
{% endhint %}

This document explains the types of files within a General Transit Feed Specification \(GTFS\) transit feed, and it defines the fields used in all of those files.

The following topics are covered in this document:

1. [Term definitions]()
2. [Field types]()
3. [Dataset files]()
4. [File requirements]()
5. [Field definitions]()
   * [agency.txt]()
   * [stops.txt]()
   * [routes.txt]()
   * [trips.txt]()
   * [stop\_times.txt]()
   * [calendar.txt]()
   * [calendar\_dates.txt]()
   * [shapes.txt]()
   * [transfers.txt]()
   * [feed\_info.txt]()

## Term definitions <a id="term-definitions"></a>

The following terms are used throughout this document:

* **Dataset**: A complete set of files defined by this specification reference. Any alteration to the dataset creates a new version of the dataset. Publish datasets at a public, permanent URL, which includes the zip file name. For example, https://www.agency.org/gtfs/gtfs.zip.
* **Record**: A basic data structure comprised of a number of different field values that describe a single entity, such as a transit agency, stop, or route. Records are represented, in a table, as a row.
* **Field**: A property of an object or entity. Represented, in a table, as a column.
* **Field value**: An individual entry in a field. Represented, in a table, as a single cell.
* **Required**: The field must be included in the dataset, and a value must be provided in that field for each record.
  * Some required fields permit an empty string as a value. To enter an empty string, just omit any text between the commas for that field. Note that `0` is interpreted as "a string of value `0`," which is different from an empty string.
* **Optional**: The field can be omitted from the dataset. If you choose to include an optional column, some of the entries in that field can be empty strings.
  * To enter an empty string, just omit any text between the commas for that field. Note that `0` is interpreted as "a string of value `0`," which is different from an empty string. An omitted field is equivalent to a field that is entirely empty.
* **Conditionally required**: The field or file is required under certain conditions, which are outlined in the field or file description. Outside of these conditions, this field or file is optional.
* **Service day**: A time period used to indicate route scheduling. The exact definition of service day varies from agency to agency, but service days often don't correspond to calendar days. A service day may exceed 24:00:00 if service begins on one day and ends on a following day. For example, service that runs from 08:00:00 on Friday to 02:00:00 on Saturday could be denoted as running from 08:00:00 to 26:00:00 on a single service day.

## Field types <a id="field-types"></a>

The following types of fields are used throughout the General Transit Feed Specification \(GTFS\) transit feed:

* **Color**: A color that's encoded as a six-digit hexadecimal number. Refer to [HTML color codes](https://htmlcolorcodes.com/) to generate valid values. Note that the leading "\#" is not included.
  * Example, `FFFFFF` for white, `000000` for black, or `0039A6` for the A,C,E lines of a service.
* **Date**: A service day that's given in the `YYYYMMDD` format. Because the time within a service day can be above 24:00:00, a service day often contains information for the subsequent days.
  * Example, `20180913` for September 13th, 2018.
* **Email**: An email address.
  * Example, `ex@gmail.com`.
* **Enum**: An option that comes from a set of predefined constants defined in the "Description" column.
  * Example, The `route_type` field of [`routes.txt`]() contains a `0` for trams or a `1` for subways.
* **ID**: A sequence of any UTF-8 characters that uniquely identifies an entity but doesn't necessarily identify a specific record in a table. IDs defined in one TXT file are often referenced in another TXT file. An ID field value isn't meant to be displayed to the user. Any UTF-8 characters can be used, but we recommend the use of only printable ASCII characters.
  * Example: The `stop_id` field in [`stops.txt`]() is an ID. The `stop_id` field in [`stop_times.txt`]() is an ID that references `stops.stop_id`.
* **Language code**: An IETF BCP 47 language code. For an introduction to IETF BCP 47, refer to [Tags for identifying languages](http://www.rfc-editor.org/rfc/bcp/bcp47.txt) and [Language tags in HTML and XML](http://www.w3.org/International/articles/language-tags/).
  * Example: `en` for English, `en-US` for American English, or `de` for German.
* **Latitude**: A WGS84 latitude in decimal degrees. The value must be greater than or equal to `-90.0` and less than or equal to `90.0`.
  * Example: `41.890169` for the Colosseum in Rome.
* **Longitude**: A WGS84 longitude in decimal degrees. The value must be greater than or equal to `-180.0` and less than or equal to `180.0`.
  * Example: `12.492269` for the Colosseum in Rome.
* **Non-negative float**: A floating point number greater than or equal to 0.
* **Non-negative integer**: An integer greater than or equal to 0.
* **Phone number**: A phone number.
* **Time**: A time given in the HH:MM:SS format. H:MM:SS is also accepted. The time is measured from "noon minus 12 hours" at the beginning of the service day. This is effectively midnight, except for days on which daylight savings time changes occur. For times after midnight, enter the time as a value greater than 24:00:00 in HH:MM:SS local time for the day on which the trip schedule begins.
  * Example: `14:30:00` for 2:30 PM or `25:35:00` for 1:35 AM on the next day.
* **Text**: A string of UTF-8 characters that is meant to be displayed, and so must be human readable.
* **Timezone**: A timezone from the [Time Zone Database](https://www.iana.org/time-zones). Timezone names never contain the space character but can contain an underscore. For a list of valid values, refer to [List of tz database time zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones).
  * Example: `Asia/Tokyo`, `America/Los_Angeles`, or `Africa/Cairo`.
* **URL**: A fully qualified URL that includes `http://` or `https://`, and any special characters in the URL must be correctly escaped. For a description of how to create fully qualified URL values, see [W3C URI recommendations](http://www.w3.org/Addressing/URL/4_URI_Recommentations.html).

## Dataset files <a id="dataset-files"></a>

This specification defines the following files and their associated content:

| Filename | Required | Definition |
| :--- | :--- | :--- |
| [`agency.txt`]() | Required | Defines one or more transit agencies that have services represented in the dataset. |
| [`stops.txt`]() | Required | Defines stops where vehicles pick up or drop off riders. Also defines stations and station entrances. |
| [`routes.txt`]() | Required | Defines transit routes. A route is a group of trips that are displayed to riders as a single service. |
| [`trips.txt`]() | Required | Defines trips for each route. A trip is a sequence of two or more stops that occur during a specific time period. |
| [`stop_times.txt`]() | Required | Provides the times when a vehicle arrives at and departs from individual stops for each trip. |
| [`calendar.txt`]() | Conditionally required | Defines service dates when service is available for particular routes. Uses a weekly schedule. This file specifies start and end dates of service, as well as the days of the week when service is available. This file is required unless all of the dates of service are defined in [`calendar_dates.txt`](). |
| [`calendar_dates.txt`]() | Conditionally required | Defines exceptions for the services defined in the [`calendar.txt`]() file. If [`calendar.txt`]() is omitted, then [`calendar_dates.txt`]() is required and must contain all dates of service. |
| [`shapes.txt`]() | Optional | Defines rules to map vehicle travel paths, sometimes referred to as route alignments. |
| [`transfers.txt`]() | Optional | Defines rules for how connections are made at transfer points between routes. |
| [`feed_info.txt`]() | Optional | Provides additional information about the feed itself, such as publisher, version, and expiration information. |

## File requirements <a id="file-requirements"></a>

The following requirements apply to the format and contents of your files:

* All files in a General Transit Feed Spec \(GTFS\) feed must be saved as comma-delimited text.
* The first line of each file must contain field names. Each subsection of the [Field definitions]() section corresponds to one of the files in a GTFS dataset. They list the field names you can use in that file.
* All field names are case sensitive.
* Field values can't contain tabs, carriage returns, or new lines.
* Field values that contain quotation marks or commas must be enclosed within quotation marks. In addition, each quotation mark in the field value must be preceded with a quotation mark. This is consistent with how Microsoft Excel outputs comma-delimited \(CSV\) files. For more information on the CSV file format, see [Common format and MIME type for comma-separated values \(CSV\) files](http://tools.ietf.org/html/rfc4180). The following example demonstrates how field values appear in a comma-delimited file:
  * Original field value: `Contains "quotes", commas, and text`
  * Field value in CSV file: `"Contains ""quotes"", commas, and text"`
* Field values must not contain HTML tags, comments, or escape sequences.
* Remove any extra spaces between fields or field names. Many parsers consider the spaces to be part of the value, which may cause errors.
* Each line must end with a CRLF or LF linebreak character.
* Encode files in UTF-8 to support all Unicode characters. Files that include the Unicode byte-order mark \(BOM\) character are acceptable. For more information on the BOM character and UTF-8, see the [Unicode FAQ](http://unicode.org/faq/utf_bom.html#BOM).
* All dataset files must be zipped together.

