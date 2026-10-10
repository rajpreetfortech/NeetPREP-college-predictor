# NEETPrep College Predictor

A mobile-first NEET UG college prediction tool that estimates All India Rank (AIR), groups possible government MBBS colleges into Safe, Moderate and Reach categories, and captures student leads with UTM attribution.

## Live Demo

**Web app:** https://script.google.com/macros/s/AKfycby8Z169EqdTUOca3JzPT5g7dmWWktocIMLcf0YHTMmteuPL8mK6gGe21zMK5qygY_3u/exec

## Problem

NEET aspirants know their score but may not know their approximate rank or which colleges to research. This tool provides an initial shortlist using supplied NEET 2025 score-to-rank anchors and indicative college closing ranks.

## Features

- NEET score input from 0 to 720
- Category selection: UR, EWS, OBC, SC and ST
- Home-state selection
- Name and 10-digit Indian mobile number validation
- College predictions grouped into Safe, Moderate and Reach
- Home-state badges and helpful empty states
- Lead storage with timestamp, score, category, state, predicted AIR and UTM parameters
- Funnel tracking for `page_view`, `form_start`, `form_submit` and `result_view`
- Test-lead marking for development and QA

## Tech Stack

- **Frontend:** HTML, CSS and JavaScript
- **Backend:** Google Apps Script
- **Database and analytics:** Google Sheets
- **Hosting:** Google Apps Script Web App

## Project Files

- `Code.gs` — serves the web app, provides college and rank data, validates and saves leads, and logs events.
- `Index.html` — contains the responsive interface, form validation, prediction logic, results display and event tracking.

## Setup and Deployment

1. Create a Google Sheet for lead and event storage.
2. Open **Extensions → Apps Script** from that spreadsheet.
3. Add `Code.gs` and an HTML file named `Index`.
4. Add the project code and save.
5. Run the `setup()` function once and authorize the requested permissions.
6. Select **Deploy → New deployment → Web app**.
7. Configure access appropriately for the intended public demo and deploy.
8. Open the `/exec` URL and test a submission.

Use the deployed `/exec` URL for sharing and testing. If you change the code, update the existing deployment with a new version.

## Data Storage

The bound Google Sheet contains:

- **Leads:** timestamp, name, phone, score, category, home state, predicted AIR, UTM source, UTM medium, UTM campaign and test-lead flag.
- **Events:** timestamp, event name, UTM attribution, device, score band, category, state, bucket counts and CTA type.

The lead sheet contains personal information. It is not included in this repository and should not be made publicly accessible. Share only a view of the lead data with phone numbers masked.

## Prediction Method

The tool uses linear interpolation between the supplied NEET 2025 score-to-AIR anchor points. It compares the estimated AIR against the selected category's college closing rank:

- **Safe:** AIR at or below 85% of the closing rank
- **Moderate:** AIR above 85% and at or below 100%
- **Reach:** AIR above 100% and at or below 115%
- Colleges beyond the Reach threshold are excluded.

Each bucket displays at most 10 colleges, sorted by closing rank.

## Data Disclaimer

The supplied college closing ranks and score-to-rank anchors are indicative assignment data, not official MCC/NTA data or a guarantee of admission. State quota, seat availability, eligibility and counselling rules may change outcomes.

## AI Usage

AI assistance was used to support implementation, debugging, validation planning, documentation and product decisions. The deployed app and its behavior were tested against the assignment requirements.

## Limitations and Future Improvements

Potential next steps include duplicate-phone checks or OTP verification, a genuine counselling request flow, a WhatsApp result-sharing feature, basic SEO and a dashboard for lead-source performance.
