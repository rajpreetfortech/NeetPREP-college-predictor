# Product Requirements Document — NEETPrep College Predictor

## 1. The Problem

After NEET results, students often know their score but struggle to understand their approximate rank and which government MBBS colleges they should explore. I wanted to build a simple, mobile-friendly tool that helps students take the first step while helping NEETprep connect with interested aspirants.

## 2. Who Is It For?

NEET UG aspirants aged 17–20 and their parents, particularly students who know their score, category and home state but need a clearer idea of their possible college options.

## 3. What I Built

I built a working, mobile-first NEET college predictor that takes students from entering their details to exploring a college shortlist.

- **Score-to-rank prediction:** Estimates All India Rank (AIR) using the supplied NEET 2025 score-to-rank data.
- **College recommendations:** Groups eligible government MBBS colleges into Safe, Moderate and Reach categories using the supplied closing ranks.
- **Personalized results:** Supports category and home-state selection, highlights home-state colleges, and displays up to 10 colleges per category with helpful empty states.
- **Lead capture and validation:** Collects the required student details, validates the score and mobile-number format, and checks for duplicate phone numbers in non-test submissions.
- **Google Sheets integration:** Stores lead details, predicted rank, timestamps and UTM campaign information.
- **Funnel analytics:** Tracks page views, form starts, submissions and result views, including useful details about the student's selected category, state and result buckets.
- **Acquisition tracking:** Uses separate UTM-tagged links for LinkedIn, WhatsApp and Instagram to understand where traffic comes from.
- **WhatsApp sharing:** Allows users to share the predictor and records supported CTA clicks.
- **Analytics dashboard:** Brings together traffic, submissions, result views, acquisition sources and lead counts for easier review.
- **Test-lead identification:** Separates test submissions from genuine leads to support testing and more reliable reporting.
- **Mobile-friendly experience:** Includes form validation, a clear results interface, home-state indicators and a disclaimer explaining that predictions are estimates.

## 4. What I Prioritized

I focused first on getting the complete journey working: a student visits the page, enters their details, receives a prediction, and generates a trackable lead record. I used HTML, CSS, JavaScript, Google Apps Script and Google Sheets to keep the solution lightweight and practical to deploy.

## 5. Note on future imporvement
Features such as OTP-based phone verification, side-by-side college comparisons, advanced filters and automated counselling reminders remain future improvements. The counselling CTA does not currently arrange a callback, so a complete counselling-request workflow would need to be built separately.

## 6. How I Will Measure Success

My initial target is for **at least 30 out of every 100 recorded page views to lead to a valid, genuine submission**.

I'll compare valid, non-test lead submissions with recorded page views to understand how well the predictor turns visits into leads. Since one person may visit more than once, this is a useful starting measure rather than an exact count of unique visitors.

I'll also look at form starts, result views and acquisition sources to identify where students drop off and which channels bring in genuine leads.

## 7. Technology

- **Frontend:** HTML, CSS and JavaScript
- **Backend:** Google Apps Script
- **Storage and analytics:** Google Sheets
- **Hosting and version control:** Google Apps Script Web App and GitHub

## 8. How AI Helped Me Build It

I used AI as a building partner throughout this project. We worked through the process step by step from shaping the product requirements and planning the user journey to writing and debugging code, improving the interface, setting up analytics, checking edge cases and refining the documentation.

I brought the assignment requirements, made product decisions, tested the deployed features and used AI to work through problems and explore better approaches. This collaboration helped me move from an idea to a working, measurable product while learning along the way.

For me, the value of AI was not simply generating code. It was having a partner to brainstorm with, ask questions, challenge assumptions and help me keep moving whenever I got stuck. I remain responsible for the final implementation, the decisions made and the accuracy of the claims in this document.
