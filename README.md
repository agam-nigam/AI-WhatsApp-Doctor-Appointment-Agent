# AI-Powered WhatsApp Appointment Management System

An AI-driven appointment management platform that enables patients to book, reschedule, view, and cancel appointments directly through WhatsApp. The system integrates Google Gemini, WhatsApp Business API, Stripe, Google Sheets, and n8n to automate the complete appointment lifecycle.

## Features

### Appointment Management

* Book appointments through natural language conversations on WhatsApp.
* View upcoming appointments.
* Reschedule existing appointments.
* Cancel appointments.
* Multi-patient support under a single WhatsApp account.

### AI-Powered Conversational Assistant

* Powered by Google Gemini.
* Context-aware conversations using memory management.
* Dynamic appointment slot selection.
* Intelligent validation of user inputs and booking requests.

### Payment Processing

* Online payments through Stripe.
* Automated payment verification using Stripe webhooks.
* Payment confirmation notifications.
* Automated refund handling for cancelled appointments.

### Automated Notifications

* Appointment confirmation messages.
* Payment confirmation messages.
* Daily appointment reminders.
* Cancellation and refund notifications.

## Technology Stack

### AI & Automation

* Google Gemini
* n8n
* Prompt Engineering

### Communication

* WhatsApp Business Cloud API

### Payments

* Stripe API
* Stripe Webhooks

### Data Storage

* Google Sheets

### Workflow Architecture

* Event-Driven Architecture
* Webhook-Based Integrations

## System Architecture

```text
Patient
   │
   ▼
WhatsApp Business API
   │
   ▼
n8n Workflow Engine
   │
   ├────────► Google Gemini
   │
   ├────────► Google Sheets
   │
   └────────► Stripe
```

## Core Workflows

### 1. Appointment Booking

* User initiates conversation through WhatsApp.
* AI assistant collects patient information.
* Available appointment slots are generated dynamically.
* User selects preferred date and time.
* Appointment record is created.
* Payment option is selected.
* Confirmation message is sent.

### 2. Payment Verification

* Stripe webhook detects successful payment.
* Appointment status is updated automatically.
* Payment information is stored.
* WhatsApp confirmation message is sent.

### 3. Appointment Reminder

* Daily scheduled workflow runs automatically.
* Today's appointments are retrieved.
* Personalized reminder messages are generated.
* Reminders are sent via WhatsApp.

### 4. Rescheduling

* User requests appointment rescheduling.
* Available slots are validated.
* Appointment details are updated.
* Updated confirmation is delivered.

### 5. Cancellation & Refund

* Appointment cancellation is detected.
* Payment status is verified.
* Refund is initiated automatically if payment was completed.
* User receives cancellation and refund confirmation.

## Google Sheets Schema

### Patients

| Field           |
| --------------- |
| patient_id      |
| whatsapp_number |
| name            |
| age             |
| gender          |

### Appointments

| Field                 |
| --------------------- |
| appointment_id        |
| patient_id            |
| whatsapp_number       |
| date                  |
| time                  |
| payment_method        |
| payment_status        |
| status                |
| stripe_payment_intent |

### Configuration

| Key           | Example     |
| ------------- | ----------- |
| working_hours | 10:00-18:00 |

## Key Engineering Concepts Demonstrated

* Event-Driven Architecture
* Webhooks
* REST API Integrations
* Workflow Automation
* Conversational AI
* State Management
* Payment Gateway Integration
* Automated Notifications
* Multi-System Integration
* Business Process Automation

## Future Improvements

* MongoDB integration instead of Google Sheets.
* Doctor dashboard for appointment management.
* Multi-doctor support.
* Calendar integration.
* Email notifications.
* Analytics dashboard.
* Voice appointment booking.

## Security Considerations

* API credentials are stored securely and never committed.
* Sensitive payment information is handled through Stripe.
* User data access is restricted to authorized workflows.
* Webhook-based communication reduces unnecessary API polling.

## Project Highlights

* AI-powered conversational appointment booking.
* Real-time payment verification and notifications.
* Automated reminders and refund management.
* End-to-end workflow automation using n8n.
* Integration of multiple third-party services into a unified system.

---

Developed as a full-stack workflow automation and AI integration project demonstrating real-world business process automation, payment handling, and conversational AI deployment.