# Power-Bi--Hospitality

## Overview
This dataset provides a comprehensive framework for analyzing hotel booking trends, room utilization, customer behavior, and financial performance. It spans three months (May to July), and includes dimensional metadata, booking logs, and calculated Power BI metrics tailored for strategic insights.

---

## Dataset Contents

| File Name | Description |
|----------|-------------|
| dim_date.csv | Contains date-level attributes including week number and day type |
| dim_hotels.csv | Metadata about hotel properties: location, category, and ID |
| dim_rooms.csv | Room-level metadata including class and type |
| fact_aggregated_bookings.csv | Daily aggregated booking metrics per hotel and room category |
| fact_bookings.csv | Granular transactional data for each individual booking |

---

## Table Schemas

### dim_date.csv
| Column Name | Description |
|-------------|-------------|
| date | Date (May–July) |
| mmm yy | Month and year (e.g., May 25) |
| week no | Sequential week number |
| day_type | Weekend or Weekday (Friday–Saturday = Weekend) |

---

### dim_hotels.csv
| Column Name | Description |
|-------------|-------------|
| property_id | Unique hotel ID |
| property_name | Name of the hotel |
| category | Luxury or Business class |
| city | Hotel location |

---

### dim_rooms.csv
| Column Name | Description |
|-------------|-------------|
| room_id | Room type (RT1–RT4) |
| room_class | Standard, Elite, Premium, or Presidential |

---

### 📈 fact_aggregated_bookings.csv
| Column Name | Description |
|-------------|-------------|
| property_id | Hotel ID |
| check_in_date | Booking date |
| room_category | Room type |
| successful_bookings | Number of completed bookings |
| capacity | Available rooms of that type on the date |

---

### fact_bookings.csv
| Column Name | Description |
|-------------|-------------|
| booking_id | Booking reference |
| property_id | Hotel ID |
| booking_date | Reservation date |
| check_in_date | Arrival date |
| check_out_date | Departure date |
| no_guests | Number of guests |
| room_category | Type of room booked |
| booking_platform | Booking channel |
| ratings_given | Customer rating |
| booking_status | Cancelled, Checked Out, or No Show |
| revenue_generated | Gross revenue estimate |
| revenue_realized | Net revenue after deductions based on status (Refund logic applied) |

---

## Metrics & DAX Measures

### Calculated Columns
- `wn`: Week number (`WEEKNUM(dim_date[date])`)
- `day_type`: Weekend or weekday logic based on day of week

---

### Key Measures

| Metric | Description |
|--------|-------------|
| Revenue | Total revenue realized |
| Total Bookings | Count of bookings |
| Total Capacity | Total rooms available |
| Total Successful Bookings | Count of fulfilled bookings |
| Occupancy % | Room usage ratio |
| Average Rating | Mean rating given |
| No of Days | Time period of the dataset |
| Total Cancelled Bookings | Count of cancelled bookings |
| Cancellation % | Cancelled bookings over total bookings |
| Total Checked Out | Successful stays |
| Total No Show Bookings | Booked but unattended |
| No Show Rate % | No show percentage |
| Booking % by Platform | Booking contribution per channel |
| Booking % by Room Class | Distribution across room classes |
| ADR (Average Daily Rate) | Revenue per room sold |
| Realisation % | % of bookings leading to revenue |
| RevPAR (Revenue per Available Room) | Revenue per room including unsold |
| DBRN | Daily Booked Room Nights |
| DSRN | Daily Sellable Room Nights |
| DURN | Daily Utilized Room Nights |
| WoW Change Metrics | Week-over-week % change for Revenue, Occupancy, ADR, RevPAR, Realisation, DSRN |

---

## Use Cases
- Revenue forecasting by week and room class
- Platform-wise marketing strategy effectiveness
- Booking pattern analysis (cancellations, no-shows)
- Pricing optimization via ADR and RevPAR
- Operational benchmarking across cities or hotel categories
