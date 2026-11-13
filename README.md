<div align="center">

<img src="banner.png" alt="GoHighLevel Automation Examples" width="100%">

# GoHighLevel Automation Examples

**Ready-to-build automation blueprints for GoHighLevel. No client data. No API keys.**

![GoHighLevel](https://img.shields.io/badge/GoHighLevel-CRM-D10A0A?style=for-the-badge)
![n8n](https://img.shields.io/badge/n8n-Automation-EA4B71?style=for-the-badge&logo=n8n&logoColor=white)
![Zapier](https://img.shields.io/badge/Zapier-Integrations-FF4A00?style=for-the-badge&logo=zapier&logoColor=white)
![Stripe](https://img.shields.io/badge/Stripe-Payments-635BFF?style=for-the-badge&logo=stripe&logoColor=white)
![Google Sheets](https://img.shields.io/badge/Google%20Sheets-Data-34A853?style=for-the-badge&logo=googlesheets&logoColor=white)

Built by **Adnan Jameel** | GoHighLevel Expert | 2+ years hands-on experience

</div>

---

## 📋 What's Inside

| # | Automation | Tools | Level |
|:-:|---|---|:-:|
| 1 | 📥 [New Lead to Google Sheets](#1--new-lead-to-google-sheets) | GHL, Sheets, n8n or Zapier | 🟢 Easy |
| 2 | 📅 [Booking Confirmation and Reminders](#2--booking-confirmation-and-reminders) | GHL Workflows, SMS, Email | 🟡 Medium |
| 3 | 💳 [Failed Payment Alert](#3--failed-payment-alert) | GHL, Stripe, Slack or Email | 🟡 Medium |

---

## 1 📥 New Lead To Google Sheets

> [!NOTE]
> **Goal:** Every new lead from a GHL form is saved to a Google Sheet automatically, so your team sees all leads in one place.

**How the data flows:**

```mermaid
flowchart LR
    A[Form Submitted in GHL] --> B[Webhook]
    B --> C[n8n or Zapier]
    C --> D[Google Sheets: Add Row]
    style A fill:#D10A0A,color:#fff,stroke:#D10A0A
    style D fill:#34A853,color:#fff,stroke:#34A853
```

**Steps:**
1. In GHL, create a workflow with the trigger **Form Submitted**.
2. Add the action **Webhook** (or use the GHL app in Zapier or n8n).
3. In n8n or Zapier, receive the data and map: name, email, phone, source, date.
4. Add the action **Google Sheets: Add Row**.
5. Test with a dummy lead and check the new row.

<details>
<summary><b>🛠️ Common problems and fixes</b></summary>

- **Webhook returns an error:** check the URL and make sure the workflow is published.
- **Fields come through empty:** re-map the custom values.

</details>

---

## 2 📅 Booking Confirmation And Reminders

> [!NOTE]
> **Goal:** After someone books, they get an instant confirmation and reminders. This cuts no-shows.

**How the data flows:**

```mermaid
flowchart LR
    A[Appointment Booked] --> B[Instant Confirmation]
    B --> C[Reminder 24h Before]
    C --> D[Reminder 1h Before]
    D --> E{Showed Up?}
    E -- No --> F[Rebooking Message]
    style A fill:#D10A0A,color:#fff,stroke:#D10A0A
    style F fill:#F59E0B,color:#000,stroke:#F59E0B
```

**Steps:**
1. Create a workflow with the trigger **Appointment Status: Confirmed**.
2. Send an instant SMS and email with the date, time, and a reschedule link.
3. Add a wait step and send a reminder 24 hours before.
4. Add another reminder 1 hour before.
5. If the status becomes **No Show**, send a rebooking message.
6. Test with a dummy booking.

<details>
<summary><b>🛠️ Common problems and fixes</b></summary>

- **Reminders send at the wrong time:** check the calendar and account time zone.
- **Duplicate messages:** make sure only one workflow uses this trigger.

</details>

---

## 3 💳 Failed Payment Alert

> [!NOTE]
> **Goal:** When a payment fails, your team and the customer are told right away, so revenue is not lost.

**How the data flows:**

```mermaid
flowchart LR
    A[Payment Failed in Stripe] --> B[Tag Contact]
    B --> C[Message Customer]
    B --> D[Alert Team]
    C --> E[Follow Up After 2 Days]
    style A fill:#D10A0A,color:#fff,stroke:#D10A0A
    style D fill:#635BFF,color:#fff,stroke:#635BFF
```

**Steps:**
1. Create a workflow with the trigger **Payment Failed** (or a Stripe webhook).
2. Add the tag `payment-failed` to the contact.
3. Send the customer a friendly message with a link to update their card.
4. Notify the team by internal notification, Slack, or email.
5. Add a follow-up after 2 days if the tag is still there.

<details>
<summary><b>🛠️ Common problems and fixes</b></summary>

- **Trigger does not fire:** check the Stripe connection in GHL.
- **Customer gets the message after paying:** add a condition to check the payment status first.

</details>

---

> [!TIP]
> Want to check your whole account instead? See my [GHL Audit Checklist](https://github.com/adnanjameel-ghl/ghl-audit-checklist).

<div align="center">

## 🚀 Need Something Built Or Fixed?

**I build GoHighLevel systems and fix broken ones.**

[![Upwork](https://img.shields.io/badge/Hire%20Me%20on-Upwork-14A800?style=for-the-badge&logo=upwork&logoColor=white)](https://www.upwork.com/freelancers/~01b36b5436c42666b9)
[![LinkedIn](https://img.shields.io/badge/Message%20Me%20on-LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/adnanjameel091)
[![Portfolio](https://img.shields.io/badge/View%20My-Portfolio-D10A0A?style=for-the-badge&logo=netlify&logoColor=white)](https://adnanjameelautomation.netlify.app/)

*Flexible hours with full overlap for US and UK time zones.*

</div>
