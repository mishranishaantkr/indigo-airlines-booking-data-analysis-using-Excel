# ✈️ IndiGo Airlines – Booking Data Analysis

> **A full end-to-end Data Analysis** on IndiGo Airlines' customer booking behaviour, revenue drivers, and operational efficiency — built using Excel (pivot tables & hypothesis sheets), and PowerPoint.

---

## 📌 Project Description

IndiGo Airlines is one of India's leading low-cost carriers, operating thousands of flights globally and serving millions of passengers every year. This project was undertaken as a **data analyst case study** with the objective of diving deep into real flight booking data to uncover patterns in revenue generation, customer preferences, and operational performance.

The dataset contains **51,201 booking records** spanning **36 variables**, covering three seat classes (Business, Premium Economy, Economy) and two primary sales channels (Internet and Mobile).

The analysis answers six core business questions across three themes:

| Theme | Focus |
|---|---|
| 📊 Data Understanding | Identifying data types, missing values, inconsistencies |
| 📐 Metrics & Metric Tree | Defining KPIs and building a structured revenue metric tree |
| 🔬 Hypothesis Testing | Formulating and validating six data-driven hypotheses |

---

## 🗂️ Repository Structure

```
indigo-airlines-booking-data-analysis/
│
├── data/
│   └── customer_booking_data.csv               # Raw dataset (51,201 records, 36 variables)
│
├── analysis/
│   └── Indigo_Airline_Revenue_analysis.xlsx    # Full Excel workbook with all analysis sheets
│       ├── ariline_booking_data                # Cleaned raw data
│       ├── Metric_tree                         # Revenue metric tree
│       ├── customer_preference_analysis        # Hypothesis 1 & 2 (baggage, meals)
│       ├── booking_trends_analysis             # Purchase lead time analysis
│       ├── Passenger_load_analysis             # Day/time segment load analysis
│       ├── operational_efficiency_analysis     # Flight duration variance by route
│       └── operational_efficiency_calculat     # Route-level calculations        
│                            
│
├── presentation/
│   ├── IndiGo_Airlines_Booking_Analysis.pptx  # Final 11-slide presentation
│   └── IndiGo_Airlines_Booking_Analysis.pdf   # PDF export of the presentation
│
└── README.md
```

---

## 📊 Key Findings

### Revenue Performance
- **Total Booking Value:** ₹18.34 Crore across all 51,201 records
- **Booking Conversion Rate:** 14.89% — only 7,442 of 49,964 records resulted in a completed booking
- **Average Order Value (completed bookings):** ₹24,521
- **Average Booking — Business Class (all records):** ₹4,609
- **Average Booking — Business Class (completed only):** ₹30,995

### Revenue by Seat Class
| Seat Class | Revenue (₹ Cr) | Share |
|---|---|---|
| Business | 7.64 | 41.88% |
| Premium Economy | 6.13 | 33.55% |
| Economy | 4.47 | 24.47% |

> Business class generates **42% of total revenue** despite representing only one-third of passengers.

### Revenue by Sales Channel
| Channel | Revenue Share |
|---|---|
| Internet | 91.69% |
| Mobile | 8.31% |

> Mobile is severely underperforming — a major growth opportunity.

---

## 🔬 Hypotheses Tested

| # | Hypothesis | Result |
|---|---|---|
| H1 | Extra baggage customers have higher booking amounts | ✅ Supported — avg ₹25,578 vs ₹21,426 |
| H2 | In-flight meal customers have higher booking amounts | ✅ Supported — avg ₹4,525 vs ₹3,029 |
| H3 | Business class passengers book earlier than Economy | ❌ Not supported — lead times nearly identical (~85 days) |
| H4 | Longer-stay passengers book earlier | ❌ Not supported — long-stay books later (73 days) vs short-stay (87 days) |
| H5 | Weekdays have higher passenger load than weekends | ✅ Supported — Mon (12,933) vs Sat (9,387) |
| H6 | Morning slots have the highest passenger load on weekdays | ✅ Supported — morning dominates all weekdays |

---

## ⚙️ Operational Efficiency

Flight duration variance was analysed across the **top 10% most-operated routes**. Six airports were flagged:

| Rank | Airport | Total Flights | Variance | Status |
|---|---|---|---|---|
| 1 | KIX – Kansai, Japan | 2,135 | 1.80 | 🔴 Critical |
| 2 | ICN – Incheon, South Korea | 3,714 | 1.78 | 🔴 Critical |
| 3 | PEK – Beijing, China | 598 | 1.68 | 🟠 High |
| 4 | HND – Haneda, Japan | 2,027 | 1.53 | 🟠 High |
| 5 | PER – Perth, Australia | 3,105 | 1.28 | 🟡 Medium |
| 6 | SYD – Sydney, Australia | 4,571 | 0.92 | 🟡 Monitor |

**Busiest Route:** AKLKUL — 2,680 flights

---

## 💡 Key Recommendations

1. **Monetise Business Class** — Introduce loyalty perks, lounge tie-ins, and upgrade pathways. Business class drives 42% of revenue with only 33% of passengers.
2. **Invest in the Mobile Channel** — Mobile accounts for only 8.3% of revenue. A seamless mobile app with exclusive deals could double conversions.
3. **Bundle Extra Baggage Offers** — Passengers with extra baggage spend 19% more on average. Short-stay customers (≤15 days) convert at 24% vs. 11.6% for longer stays — target them at checkout.
4. **Fix Operational Variance at KIX & ICN** — Escalate to ops management. Variance reduction lowers fuel costs and improves passenger satisfaction scores.
5. **Dynamic Weekend Pricing** — Saturday has 27% fewer passengers than Monday. Introduce weekend flash sales and early-bird promotions to stimulate demand.
6. **Premium-Price Morning Flights** — Morning slots carry the highest load across all weekdays. Introduce peak-time pricing to capture additional revenue per seat.

---

## 🛠️ Tools & Technologies

| Tool | Purpose |
|---|---|
| Microsoft Excel | Data extraction, metric calculation, hypothesis testing |
| Microsoft Excel | Pivot tables, analysis sheets, metric tree, dashboard |
| Microsoft PowerPoint | 11-slide presentation deck |
| CSV | Raw dataset storage |

---

## 📁 Data Dictionary (Selected Columns)

| Column | Type | Description |
|---|---|---|
| `booking_amount` | Numerical Continuous | Total fare paid per booking |
| `purchase_lead` | Numerical Continuous | Days between booking and flight date |
| `flight_duration_planned` | Numerical Continuous | Scheduled flight duration (hours) |
| `flight_duration_actual` | Numerical Continuous | Actual flight duration (hours) |
| `variance_of_flight_time` | Numerical Continuous | Difference between planned and actual duration |
| `num_passengers` | Numerical Discrete | Number of passengers in booking |
| `flight_hour` | Numerical Discrete | Hour of departure |
| `flight_number` | Numerical Discrete | Flight identifier |
| `sales_channel` | Categorical Nominal | Internet or Mobile |
| `seat_class` | Categorical Nominal | Business, Premium Economy, Economy |
| `Route` | Categorical Nominal | Origin-destination airport code pair |
| `booking_origin` | Categorical Nominal | Country of booking |
| `trip_type` | Categorical Nominal | Round trip or one-way |
| `flight_day` | Categorical Ordinal | Day of the week (Mon–Sun) |
| `day_segment` | Categorical Ordinal | Night, Morning, Afternoon, Evening |
| `length_of_stay_segment` | Categorical Ordinal | Short / Medium / Long stay |
| `wants_extra_baggage` | Binary | 1 = opted for extra baggage |
| `wants_preferred_seat` | Binary | 1 = opted for preferred seat |
| `wants_in_flight_meals` | Binary | 1 = opted for in-flight meals |
| `booking_complete` | Binary | 1 = booking successfully completed |

### Missing Data
- **1,214 rows** had missing values (~2.4%) — handled via exclusion for numeric aggregations
- **59 records** had `{no data}` in `sales_channel` — removed from channel-level analysis

---

## 👤 Author

**Nishant Kumar Mishra**  
Data Analyst | Excel | Business Intelligence | EDA ( Exploratory Data Analysis ) 


---

## 📄 License

This project is for educational and portfolio purposes only. The dataset is used solely for analytical case study work.
