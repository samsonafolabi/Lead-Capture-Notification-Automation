# Lead Capture & Notification Automation

**A simple, event-driven workflow that takes a web form submission and instantly turns it into a CRM record and a live team notification — built on n8n, Airtable, and Slack.**

---

## The Problem

Every minute a new lead sits unactioned is a minute closer to losing it. Small teams often rely on someone manually checking an inbox or form submissions dashboard, copying details into a spreadsheet or CRM, and then remembering to tell the right person. That gap between "someone filled out a form" and "someone on the team actually knows about it" is where leads go cold.

## The Solution

This workflow closes that gap automatically:

1. A **web form** submits directly to an n8n webhook
2. The submission is instantly written as a **new record in Airtable**, tagged with a `Status: New`
3. The team gets a **real-time Slack notification** with the lead's name, email, and message — no one has to go looking for it

From form submission to CRM record to team alert happens in seconds, with zero manual steps.

## How It Works (Architecture)

```
Web Form Submission
        |
Webhook (n8n)
        |
Create record in Airtable (Leads base)
        |
Send Slack notification (#leads channel)
```

## Stack

| Component | Tool |
|---|---|
| Workflow orchestration | [n8n](https://n8n.io) |
| Form intake | Webhook (any HTML/JS form can POST to it) |
| CRM / lead storage | Airtable |
| Team notification | Slack |

Each piece here is swappable — the webhook can accept submissions from any frontend or form builder, Airtable can be replaced with a different CRM, and Slack can be swapped for email or SMS depending on how a team communicates.

## Watch the demo here

📹 [Watch the demo video](#) *https://drive.google.com/file/d/1xc77sEg4JsIHonrvhegPazwM7HkqUHrV/view?usp=sharing*

## Why This Pattern Matters

This is a minimal example of a broader pattern: **event in → structured record out → the right person notified**, with no manual handoff in between. The same shape applies well beyond lead capture:

- New support ticket → logged + routed to the right team channel
- New job application → logged + hiring manager notified
- New order/inquiry → logged + sales notified

Main role is to demonstrate the core building blocks — webhooks, structured data writes, and real-time alerting — that scale into much larger automations.

## Workflow File

The full n8n workflow (importable JSON) is included in this repo: [`My workflow.json`](./My workflow.json)

## Built By

*[Afolabi Samson / afolabisamson20@gmail.com]*
