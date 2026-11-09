# Smart Travel Follow-Up Automation

An automated customer communication system built with n8n, Google Sheets, and Gmail.

## 1. Project Overview

Travel agencies often need to remind customers about upcoming trips and follow up after their return. Managing these communications manually can become difficult, especially when handling multiple customers.

This project automates customer follow-ups by checking trip dates daily and sending timely, personalized emails.

## 2. The Problem

Manually tracking customer departure and return dates can lead to missed reminders, delayed communication, and poor customer follow-up.

The goal of this project is to reduce manual work and help a travel agency maintain consistent communication with its customers.

## 3. How the Automation Works

The workflow runs automatically every day and:

1. Retrieves customer trip records from Google Sheets.
2. Checks departure and return dates.
3. Identifies customers due for a reminder.
4. Sends a pre-trip email three days before departure.
5. Sends a welcome-back email one day after return.
6. Checks the Reminder Log to prevent duplicate emails.
7. Records successfully sent reminders in Google Sheets.

## 4. Key Features

- Automated daily scheduling.
- Personalized customer email messages.
- Pre-trip and post-trip communication.
- Google Sheets integration for customer records.
- Gmail integration for email delivery.
- Duplicate reminder prevention.
- Reminder logging and execution tracking.
- Africa/Lagos timezone configuration.

## 5. Technology Stack

- **n8n:** Workflow automation and orchestration.
- **Google Sheets:** Customer trip records and reminder logs.
- **Gmail:** Automated email delivery.
- **JavaScript:** Date calculations, data processing, and duplicate prevention.

## 6. Testing and Validation

The workflow was tested to confirm that:

- Customer records are retrieved and processed correctly.
- Departure and return dates are evaluated against the reminder rules.
- Eligible customers receive the appropriate email.
- Sent reminders are recorded in the Reminder Log.
- Previously sent reminders are skipped during subsequent executions.

## 7. Project Status

The workflow has been published in n8n and configured to run daily.

## 8. Skills Demonstrated

- Workflow design and automation.
- Working with external application integrations.
- Data processing and conditional logic.
- JavaScript within automation workflows.
- Date and timezone handling.
- Duplicate prevention and execution logging.
- Testing and troubleshooting automation workflows.

## 9. Privacy and Security

Customer records, personal email addresses, authentication credentials, and API tokens are not included in this public repository.

