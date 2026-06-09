# Setup Guide

## Prerequisites

- n8n
- Google Gemini API Key
- WhatsApp Business Cloud API
- Stripe Account
- Google Sheets
- Google Cloud Credentials

---

## Import Workflow

1. Open n8n.
2. Click "Import Workflow".
3. Select `workflow.json`.
4. Save the workflow.

---

## Configure Credentials

Add the following credentials in n8n:

### Google Gemini
- API Key

### Google Sheets
- Google OAuth Credentials

### WhatsApp Business API
- Access Token
- Phone Number ID

### Stripe
- Secret Key

---

## Google Sheets Structure

### Patients

| Field |
|---------|
| patient_id |
| whatsapp_number |
| name |
| age |
| gender |

### Appointments

| Field |
|---------|
| appointment_id |
| patient_id |
| whatsapp_number |
| date |
| time |
| payment_method |
| payment_status |
| status |
| stripe_payment_intent |

### Config

| Key | Value |
|------|------|
| working_hours | 10:00-18:00 |

---

## Enable Workflows

Activate:

1. Appointment Booking Workflow
2. Payment Verification Workflow
3. Payment Link Generation Workflow
4. Appointment Reminder Workflow
5. Cancellation & Refund Workflow

---

## Features

- AI-powered appointment booking
- Multi-patient support
- Appointment rescheduling
- Appointment cancellation
- Stripe payment collection
- Automated refunds
- WhatsApp notifications
- Automated appointment reminders

---

## Architecture

WhatsApp User
↓
WhatsApp Business API
↓
n8n AI Agent
↓
Google Gemini
↓
Google Sheets

Stripe ↔ n8n

---

## Security Notes

- Never commit API keys.
- Never commit Stripe secrets.
- Never commit WhatsApp access tokens.
- Use environment variables for credentials.