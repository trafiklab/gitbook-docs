# GTFS

The **General Transit Format Specification** is a format which originally was developed by Google in 2006. It's perfect for those who want to retrieve all information in one compact file.

| Well suited for | Not so suited for |
| :--- | :--- |
| Analyzing \(realtime\) transport data | Quickly getting the next departures from a stop |
| Building your own routeplanner | Quickly calculating a route from A to B |
| Getting a list of all stops | Projects where large files \(&gt;25MB\) can't be used |
| Getting the live position of public transport vehicles |  |

{% hint style="info" %}
There are hundreds of libraries, examples and demos for GTFS. You can find some at [https://github.com/andredarcie/awesome-gtfs](https://github.com/andredarcie/awesome-gtfs) and [https://github.com/CUTR-at-USF/awesome-transit](https://github.com/CUTR-at-USF/awesome-transit). 
{% endhint %}

You can read more about the exact syntax on our GTFS Data format page.

{% page-ref page="../../../public-transport-data/transport-data-formats/gtfs/" %}

## GTFS at Trafiklab

At trafiklab, we offer two GTFS feeds. The first is [GTFS Sverige 2](https://www.trafiklab.se/api/gtfs-sverige-2), which includes information for entire Sweden. We also offer[ GTFS Regional](https://www.trafiklab.se/api/gtfs-regional-beta), which consists of multiple GTFS feeds, each of which covers a region in Sweden.

|  | GTFS Sverige 2  | GTFS Regional |
| :--- | :--- | :--- |
| Geographical coverage | 100% |  |
| Transit coverage | 100% | 92% |
| Data quality | Average quality | Highest quality |
| Real-time data | Only static data | Real-time including positions |
| Historic data | Since 2012 | Not available |

### Read more

{% page-ref page="gtfs-sverige-2-static.md" %}

{% page-ref page="gtfs-regional/" %}

