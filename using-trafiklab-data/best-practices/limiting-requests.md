# Limiting requests

### Adjusting the update frequency during the day

| Interval | Number of hours | Requests per hour for one stop | Number of requests |
| :--- | :--- | :--- | :--- |
| Every 10 minutes in 6:00-6:59 | 1 | 6 | 6 |
| Every 2 minutes in 7:00-9:59 | 3 | 30 | 90 |
| Every 5 minutes in 10:00-21:59 | 12 | 12 | 144 |
| Every 10 minutes in 22:00-22:59 | 1 | 6 | 6 |
| **Total** |  |  | **246 requests per day** |

This solution will use about 7600 requests per month, which is well under the maximum of 10.000 monthly requests / 31 days per month = 322 requests per day, and will thus work perfectly.

