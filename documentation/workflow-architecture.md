# Workflow Architecture

## Overview

The Smart Travel Follow-Up Automation is built with n8n and integrates Google Sheets and Gmail to automate scheduled customer communication.

The workflow uses customer travel information to determine when pre-trip reminders and post-trip follow-ups should be sent.

## Workflow Components

| Component | Responsibility |
|---|---|
| Schedule Trigger | Initiates scheduled workflow execution. |
| Google Sheets | Retrieves customer travel records. |
| Check Reminder Dates | Evaluates departure and return dates and identifies eligible reminders. |
| Edit Fields | Organises the information required for subsequent processing. |
| Check Existing Reminder | Retrieves existing reminder records for comparison. |
| Filter Unsent Reminders | Excludes notifications that have already been logged. |
| Send Reminder Email | Sends the appropriate personalised email through Gmail. |
| Reminder Log | Stores records of sent notifications in Google Sheets. |

## How the Workflow Operates

### 1. Customer Data Retrieval

Customer names, email addresses, departure dates, return dates and reminder statuses are retrieved from the Customer Trips spreadsheet.

### 2. Date Evaluation

The Check Reminder Dates Code node evaluates each customer's travel dates against the current date.

It identifies:
- Customers departing in three days.
- Customers who returned yesterday.
- Customers who are not yet due for a reminder.

Date calculations use the Africa/Lagos timezone.

### 3. Reminder Verification

Before an email is sent, the workflow checks the Reminder Log for previously recorded notifications.

The Filter Unsent Reminders Code node compares generated ReminderKeys against existing records and excludes reminders that have already been sent.

### 4. Email Delivery

Eligible customers receive personalised pre-trip or post-trip emails through Gmail.

### 5. Reminder Logging

Following email delivery, the workflow records the corresponding reminder information in the Google Sheets Reminder Log.

## Duplicate Prevention

Each notification is assigned a unique `ReminderKey` based on the customer identifier, reminder type and relevant travel date.

This allows the workflow to recognise previously processed reminders and avoid sending the same notification again during subsequent executions.

## Design Considerations

The workflow was designed around:
- Automated and repeatable execution.
- Clear separation of customer data and reminder records.
- Date-based decision-making.
- Prevention of duplicate notifications.
- A structure that can accommodate additional customer records.

## Summary

The workflow combines scheduled execution, customer data processing, conditional logic, email delivery and reminder tracking to provide a practical solution for automated travel customer follow-ups.
