# How and When CAPTCHAs Are Displayed

## Overview

CAPTCHA is used to help protect the service from automated traffic, abuse, and other unwanted activity. While CAPTCHA could be shown on every user interaction, doing so would interrupt normal user flow and negatively affect the overall experience.

To balance security and usability, the service does not display CAPTCHA for every request. Instead, a challenge appears only when the system detects suspicious behavior or unusual traffic patterns.

---

## How CAPTCHA Is Triggered

The system continuously evaluates incoming requests and overall traffic patterns. A CAPTCHA may be triggered when a request or a group of requests differs from what is considered normal behavior.

CAPTCHA can also be enabled manually when additional protection is needed.

This approach helps protect the service without affecting most users.

> **Placeholder:** Flowchart  
> _Incoming request → Rule evaluation → CAPTCHA shown or request allowed_

---

## Conditions for Triggering CAPTCHA

Each condition listed below is evaluated independently.  
If **any one condition** is met, a CAPTCHA challenge is displayed.

### 1. High number of requests from one IP address

A CAPTCHA is triggered if more than **500 requests** are received from the same IP address within **20 minutes**.

This behavior often indicates automated scripts or bots sending requests much faster than a human user would.

---

### 2. IP address is blacklisted

A CAPTCHA is shown if a request comes from an IP address that is present on the service’s blacklist.

Blacklisted IP addresses are typically associated with suspicious or previously abusive activity.

> **Placeholder:** Link to IP blacklist management documentation

---

### 3. Traffic spike compared to normal usage

A CAPTCHA may be triggered if the number of requests in the **current hour** exceeds **twice the average** number of requests for the same hour over the **previous two weeks**.

This condition helps protect the service during sudden traffic spikes that may indicate coordinated attacks or abnormal behavior.

> **Placeholder:** Link to traffic monitoring and analytics documentation

---

### 4. Repeated identical payloads

A CAPTCHA is triggered if the same request payload is sent more than **five times within 30 seconds**.

This pattern is common in spam attempts or automated retries that repeatedly submit identical data.

---

### 5. CAPTCHA enabled manually by administrators

Administrators can manually enable CAPTCHA through the admin panel for selected requests or scenarios.

This option is typically used during:

- Active attacks or abuse not yet covered by automated rules
- Maintenance periods that require additional protection

> **Placeholder:** Screenshot of CAPTCHA settings in the admin panel  
> **Placeholder:** Link to admin panel documentation

---

## What Happens When CAPTCHA Is Triggered

When a CAPTCHA is triggered:

- The user is presented with a CAPTCHA challenge
- The request continues only after the challenge is completed successfully
- If the user does not complete the CAPTCHA, the request may be delayed or abandoned by the user

> **Placeholder:** Example CAPTCHA challenge shown to the user

---

## Who Might Encounter a CAPTCHA

A CAPTCHA may appear for:

- Users sending many requests in a short period of time
- Users on shared or previously flagged networks
- Automated tools or scripts
- Legitimate users during periods of unusual traffic

In most cases, CAPTCHA is temporary and stops appearing once activity returns to normal.

---

## See Also

- [What is CAPTCHA?](#placeholder)
- [Accessing the admin panel](#placeholder)
- [Security and abuse prevention overview](#placeholder)
- [Traffic monitoring and analytics](#placeholder)
- [IP blacklist management](#placeholder)

---
