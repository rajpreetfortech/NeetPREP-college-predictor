# Product Requirements Document — NEETPrep College Predictor

**Problem:** NEET aspirants often know their exam score but need help estimating their All India Rank (AIR) and identifying government MBBS colleges to research. The predictor provides an initial shortlist and helps NEETprep capture relevant student leads.

**Target user:** NEET UG aspirants aged 17–20 and their parents, especially mobile users who know their score, category and home state but not their estimated rank.

**MVP scope:** A mobile-first page collects NEET score, category, home state, name and mobile number. It estimates AIR using supplied score-to-rank anchors, groups colleges into Safe, Moderate and Reach, and displays a data disclaimer. Lead records and UTM attribution are stored in Google Sheets, alongside funnel events for page views, form starts, submissions and result views.

**What I cut and why:** OTP, duplicate-phone detection, an admin dashboard and WhatsApp result sharing were deferred to prioritize a working prediction-to-lead journey within the assignment timeline. The counselling CTA currently tracks interest but does not arrange a callback; a real request workflow would require a confirmed destination and process.

**Success metric:** Target a 30% visitor-to-valid-lead conversion rate during initial user testing. Calculate this using valid non-test lead submissions divided by recorded page views; because repeat visits may occur, this is an initial proxy rather than a unique-visitor conversion rate.

**Implementation:** HTML, CSS and JavaScript, hosted with Google Apps Script, with Google Sheets for lead storage and event logging.
