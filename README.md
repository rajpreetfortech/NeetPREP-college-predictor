# 🎓 NEETPrep College Predictor

### Turn your NEET UG score into a college shortlist.

A mobile-first college prediction web app that helps NEET aspirants estimate their All India Rank (AIR) and explore indicative government MBBS college options across **Safe, Moderate, and Reach** categories.

Built as a product assignment to demonstrate product thinking, frontend development, lead capture, acquisition tracking, and analytics.

<p align="center">

[**🚀 Open Live Predictor**](https://script.google.com/macros/s/AKfycby8Z169EqdTUOca3JzPT5g7dmWWktocIMLcf0YHTMmteuPL8mK6gGe21zMK5qygY_3u/exec)

</p>

---

## 📌 Overview

NEET aspirants often know their exam score but may be unsure about their approximate rank and which colleges to research.

NEETPrep College Predictor provides an initial shortlist using supplied NEET 2025 score-to-rank anchors and indicative college closing ranks. It combines a student-facing prediction experience with a lightweight lead-capture and analytics workflow.

> **Please note:** Predictions are indicative and intended for exploration. They do not guarantee admission.

## ✨ Key Features

| Feature | Description |
|---|---|
| 🎯 Score-based prediction | Accepts NEET scores from 0 to 720 and estimates AIR using linear interpolation between supplied rank anchors. |
| 🏷️ Category selection | Supports UR/General, EWS, OBC, SC and ST categories. |
| 📍 Home-state selection | Uses the selected home state to identify and highlight relevant colleges in the results. |
| 🧭 College buckets | Groups eligible college options into Safe, Moderate and Reach based on estimated AIR and closing ranks. |
| 📋 Clear results | Displays college options in closing-rank order, with up to 10 colleges per bucket and helpful empty states. |
| 📱 Mobile-first interface | Provides a responsive, student-friendly interface for mobile and desktop screens. |
| ✅ Form validation | Validates required inputs, score range and Indian mobile-number format before accepting a submission. |
| 🛡️ Duplicate submission checks | Checks for duplicate phone numbers among non-test submissions. This is format and duplicate validation, not OTP-based verification. |
| 📊 Lead capture | Stores submitted lead details, predicted AIR, timestamps and acquisition parameters in Google Sheets. |
| 🔗 UTM attribution | Uses campaign parameters to distinguish traffic from LinkedIn, WhatsApp and Instagram links. |
| 📈 Event tracking | Records page views, form starts, submissions, result views and CTA clicks for funnel analysis. |
| 🧪 Test-lead marking | Separates test submissions from real leads for development and QA. |
| 💬 WhatsApp sharing | Lets users share the predictor through WhatsApp and tracks share-button clicks. |
| 📉 Analytics dashboard | Summarizes funnel activity, acquisition sources and lead counts using Google Sheets. |

## 🖥️ Product Flow

1. **Visit:** A student opens the predictor using the live URL or a campaign link.
2. **Enter details:** The student provides their NEET score, category, home state, name and mobile number.
3. **Validate:** The app checks the submitted information.
4. **Predict:** The app estimates AIR and compares it with the supplied college closing-rank data.
5. **Explore:** The student views Safe, Moderate and Reach college options, including home-state indicators where applicable.
6. **Capture and analyze:** The backend stores the submission and logs relevant analytics events.
7. **Share:** The student can share the predictor through WhatsApp.

## 🧮 Prediction Methodology

The predictor uses the supplied NEET 2025 score-to-rank anchor points.

- **AIR estimation:** Linear interpolation between adjacent anchor points.
- **Safe:** Estimated AIR is at or below 85% of a college's closing rank.
- **Moderate:** Estimated AIR is above 85% and at or below 100% of the closing rank.
- **Reach:** Estimated AIR is above 100% and at or below 115% of the closing rank.
- **Display limit:** Up to 10 colleges per bucket, sorted by closing rank.

The prediction depends on the supplied data and methodology. Actual counselling outcomes may differ.

## 🛠️ Technology Stack

| Layer | Technology |
|---|---|
| Frontend | HTML, CSS, JavaScript |
| Backend | Google Apps Script |
| Data storage | Google Sheets |
| Hosting | Google Apps Script Web App |
| Analytics | Custom event logging and Google Sheets dashboard |
| Version control | Git and GitHub |

## 📂 Project Structure

```text
neetprep-college-predictor/
├── Code.gs       # Web app backend, validation, lead storage and event logging
├── Index.html    # Responsive interface, form, results and sharing
├── README.md     # Project documentation
└── PRD.md        # Product requirements and scope
```

## 📊 Data Collection and Analytics

The connected Google Spreadsheet contains two primary data tabs:

### Leads
Stores the submission timestamp, name, phone number, score, category, home state, predicted AIR, UTM source, UTM medium, UTM campaign and test-lead flag.

### Events
Stores the timestamp, event name, UTM attribution, device information, score band, category, state, result-bucket counts and CTA type where applicable.

### Tracked events

| Event | Purpose |
|---|---|
| `page_view` | Records a predictor visit and available acquisition/device information. |
| `form_start` | Records the beginning of the form flow. |
| `form_submit` | Records a submission and relevant score/category/state attributes. |
| `result_view` | Records result-display activity and bucket counts. |
| `cta_click` | Tracks supported calls to action, including WhatsApp sharing. |

The dashboard uses these events to understand acquisition and funnel activity. Event totals should not be interpreted as unique visitors unless unique-user tracking is implemented.

## 🔗 Campaign Tracking

Separate UTM-tagged links support acquisition analysis across:

- **LinkedIn:** Organic professional sharing.
- **WhatsApp:** Group and referral sharing.
- **Instagram:** Story-based sharing.

Campaign parameters are recorded where available, allowing traffic and lead sources to be compared in the analytics dashboard.

## 🚀 Setup and Deployment

1. Create a Google Spreadsheet for lead and event storage.
2. Open **Extensions → Apps Script** from the spreadsheet.
3. Add the backend code as `Code.gs`.
4. Add an HTML file named `Index` and include the frontend code.
5. Save the project and run `setup()` once, if required by the project code. Authorize the requested permissions.
6. Select **Deploy → New deployment → Web app**.
7. Configure access appropriately for the intended audience and deploy.
8. Open the deployed `/exec` URL and test the form, results, storage and event logging.
9. When changing the deployed code, update the deployment to a new version as needed.

Use the deployed web app URL for public demonstrations. Keep the connected spreadsheet private.

## 🔐 Privacy and Data Handling

- The connected lead spreadsheet contains personal information and should remain access-restricted.
- Phone numbers should be masked in screenshots and evaluation copies.
- Test leads should be distinguished from genuine leads when reporting results.
- The app validates mobile-number format and checks duplicates; it does not establish phone ownership through OTP verification.

## 🤖 AI Usage

AI assistance supported implementation, debugging, documentation and product decisions. The final code, behavior and metrics should be reviewed and validated against the actual deployed application before making claims about functionality.

## ⚠️ Disclaimer

This project uses supplied assignment data and is not an official counselling platform. Score-to-rank estimates and college closing ranks are indicative. Admission depends on official counselling data, eligibility, category, quota, seat availability and applicable rules.

#### 🔮 Future Improvements & Product Roadmap

The following enhancements could further improve the predictor's accuracy, student experience, operational reliability and engagement. They would be prioritized based on student feedback, data quality, implementation effort and expected impact.

### 🎓 1. College Discovery & Comparison
- **College comparison tool:** Enable students to compare 2–3 colleges using verified information such as closing ranks, location, counselling quota, fees and course availability.
- **Advanced college filters:** Allow filtering by state, college type, closing rank and fee range, subject to reliable data availability.
- **More personalized recommendations:** Refine shortlists using relevant counselling quotas and eligibility criteria.

### 📊 2. Analytics & Growth
- **Enhanced funnel analytics:** Track form abandonment, submission completion and result views to identify friction in the student journey.
- **Lead-source performance:** Compare acquisition channels using valid-lead conversion rates rather than raw submission counts alone.
- **CTA performance:** Measure which calls to action generate meaningful engagement.
- **Session-level tracking:** Distinguish sessions from individual events to support more reliable conversion analysis.

### 🔐 3. Security & Lead Quality
- **Rate limiting and bot protection:** Reduce automated spam and repeated abusive submissions.
- **OTP-based phone verification:** Explore verifying phone ownership to improve lead quality.
- **Stronger data-quality checks:** Identify duplicates, invalid contact details and test submissions more consistently.

### 📅 4. Counselling Updates & Student Engagement
- **Opt-in counselling reminders:** Let students choose whether they want reminders about official counselling registration dates, deadlines and important announcements.
- **SMS notification consent:** Collect explicit permission before sending recurring counselling updates by SMS, explain the message purpose and frequency, and provide a simple way to withdraw consent.
- **Counselling and exam news:** Surface relevant updates with links to official sources, helping students distinguish verified announcements from general information.

### 🛠️ 5. Reliability & Trust
- **Automated testing:** Expand tests for rank estimation, college-bucket thresholds, form validation and edge cases.
- **Updated counselling data:** Incorporate verified and current college, quota and closing-rank information.
- **Prediction transparency:** Explain how AIR estimates and Safe, Moderate and Reach classifications are calculated.
- **Privacy and accessibility:** Improve consent management, data handling, accessibility and usability across devices.

These enhancements are planned opportunities rather than features currently available in the deployed version.
---

**Built to demonstrate product thinking, rapid prototyping, data-driven decision-making and end-to-end execution.**


> “This project is a reflection of where I am today, not the limit of what I can do. I’m eager to learn, take ownership, and prove my capabilities through the work I deliver.”
> Thank You for Visitng
