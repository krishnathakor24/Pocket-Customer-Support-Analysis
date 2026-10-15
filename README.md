# Pocket Customer Support Analysis (Excel Case Study)

An interactive Excel dashboard that analyzes **239 support tickets** (26 May - 12 Jul 2026) for a consumer voice-recorder app ("Pocket"), built as a case study for a **Customer Support Specialist** role. It answers where tickets come from, how fast the team responds and resolves, how satisfied customers are and whether the new app release (v3.2) changed anything.

<img width="959" height="396" alt="image" src="https://github.com/user-attachments/assets/67a478af-5e95-47d1-b804-fef0663eed73" />

## Business Questions
- Which issue categories generate the most tickets?
- Do email and chat perform differently on speed and satisfaction?
- Are we meeting the first-response SLA?
- How long do tickets take to resolve?
- How satisfied are customers, and how many even rate us?
- Did app version 3.2 change ticket volume, mix, or satisfaction?

## Dataset
| Item | Detail |
|---|---|
| Records | 239 tickets |
| Period | 26 May 2026 - 12 Jul 2026 |
| Channels | Email, Chat |
| Categories | 8 (device pairing, device battery, sync, transcription, billing, returns/warranty, account/login, other) |
| App versions | 3.1, 3.2 (v3.2 began rolling out 22 Jun 2026) |
| Platforms | iOS, Android |
| Status | 234 Resolved, 3 Open, 2 Pending customer |

A data dictionary sheet documents every column.

## Approach
1. **Cleaned and structured** the raw ticket export in Excel.
2. **Engineered helper columns** to turn raw numbers into reportable buckets:
   - `month`: extracted from the ticket creation date
   - `csat_rated` / `csat_bucket`: Rated vs Not Rated; 1-2 = Dissatisfied, 3 = Neutral, 4-5 = Satisfied
   - `time_taken_to_resolve`: 1 Day (up to 24h), 2 Days (24-48h), More than 2 days (over 48h)
   - `sla_first_response_met`: SLA met if first response was within 6 hours
3. **Built 8 pivot tables**, one chart each, one per business question.
4. **Assembled a single dashboard sheet** with the charts and interactive slicers for filtering.

## Dashboard Contents
| # | View |
|---|---|
| 1 | Total tickets by category |
| 2 | Tickets by channel |
| 3 | Tickets by app version |
| 4 | Tickets by OS |
| 5 | Customer satisfaction (Satisfied / Neutral / Dissatisfied / Not Rated) |
| 6 | Rated vs Not Rated |
| 7 | Time taken to resolve |
| 8 | First-response SLA |

## Key Insights
- **Top drivers:** Device pairing (51) is the largest category, followed by device battery and transcription (39 each).
- **Chat beats email on speed.** Average first response is about **1.4 hours on chat vs 7.1 hours on email**. Chat met the 6-hour first-response SLA on 100% of tickets; email on only about 46%. Overall SLA compliance is about 72%.
- **Resolution speed:** About 66% of tickets resolve within a day; 23 tickets (about 10%) took more than 2 days.
- **Billing and transcription hurt satisfaction.** They have the lowest average CSAT (about 2.4 and 2.5 out of 5) and some of the longest resolution times (about 49h for billing, 32h for transcription).
- **Release signal:** Transcription tickets jumped from **10 on v3.1 to 29 on v3.2**, even though v3.2 had only about three weeks of data. Average CSAT also dipped from about 3.6 (v3.1) to 3.2 (v3.2).
- **Feedback gap:** About 43% of tickets (102 of 239) have no satisfaction rating, so CSAT reflects only part of the customer base.
- Among rated tickets, about 48% are satisfied, 31% neutral, and 20% dissatisfied.

## Recommendations
1. **Escalate the transcription issue** in v3.2 to product or engineering, and consider a support macro and status note while it is open.
2. **Prioritize billing tickets**: they are slow and drive the lowest CSAT; consider a dedicated queue or refund playbook.
3. **Raise CSAT response rate** with a one-click rating prompt on ticket closure.

## Author
Krishna Thakor · [LinkedIn](https://www.linkedin.com/in/krishnamaheshchandrathakor/) · [Email](mailto:krishnathakor2411@gmail.com)
