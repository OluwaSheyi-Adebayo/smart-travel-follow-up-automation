# Setup and Configuration Guide

## Overview

This guide explains how to import and configure the Smart Travel Follow-Up Automation in an n8n workspace.

## Prerequisites

Before setting up the workflow, ensure you have:

- An n8n account.
- A Google account with access to Google Sheets.
- A Gmail account for sending reminder emails.
- The exported workflow JSON file from this repository.

## 1. Import the Workflow

1. Log in to your n8n workspace.
2. Select the option to import a workflow.
3. Upload `smart-travel-automation.json`.
4. Review the imported workflow and its connected nodes.

## 2. Configure Google Sheets

Connect your Google account to n8n.

The workflow uses two spreadsheet tabs:

**Customer Trips**

Contains customer information and travel schedules, including names, email addresses, departure dates, return dates and reminder statuses.

**Reminder Log**

Stores records of previously sent notifications and their corresponding ReminderKeys.

Ensure the spreadsheet structure and column mappings match the imported workflow.

## 3. Configure Gmail

1. Open the Gmail sending node.
2. Connect your Gmail account using the required OAuth authentication.
3. Verify the recipient email mapping.
4. Confirm the subject and message content.
5. Send a test email to validate the connection.

## 4. Verify Workflow Settings

Before testing, confirm:

- The workflow timezone is set to `Africa/Lagos`.
- The Schedule Trigger has the intended execution interval.
- Google Sheets credentials and spreadsheet references are correct.
- Gmail authentication is active.
- Required node connections and field mappings are intact.

## 5. Test the Workflow

Use controlled customer records with suitable departure and return dates.

Verify that:

- Customers due for pre-trip reminders are identified correctly.
- Customers due for post-trip follow-ups are identified correctly.
- Emails are delivered to the intended recipients.
- Sent notifications appear in the Reminder Log.
- Previously logged ReminderKeys are excluded during subsequent executions.

## 6. Activate the Workflow

After successful testing:

1. Review the complete workflow.
2. Confirm all external connections are working.
3. Activate or publish the workflow using the available n8n controls.
4. Monitor subsequent executions to verify scheduled operation.

## Important Notes

- External credentials are not included in the exported workflow and must be configured independently.
- Keep customer information and authentication credentials private.
- Use appropriate test records before processing actual customer data.
- Ensure the Google Sheets structure remains consistent with the workflow's field mappings.

## Completion

Once configured and activated, the workflow can automatically evaluate customer travel schedules and process eligible email reminders according to its configured rules.
