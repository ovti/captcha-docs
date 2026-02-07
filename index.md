# How and When CAPTCHAs Are Displayed

## Table of Contents

1. [Overview](#overview)
2. [How CAPTCHA Is Triggered](#how-captcha-is-triggered)
3. [Conditions for Triggering CAPTCHA](#conditions-for-triggering-captcha)
   - [High number of requests](#1-high-number-of-requests-from-one-ip-address)
   - [IP address is blacklisted](#2-ip-address-is-blacklisted)
   - [Traffic spike](#3-traffic-spike-compared-to-normal-usage)
   - [Repeated identical payloads](#4-repeated-identical-payloads)
   - [Manual admin trigger](#5-captcha-enabled-manually-by-administrators)
4. [What Happens When CAPTCHA Is Triggered](#what-happens-when-captcha-is-triggered)
5. [Who Might Encounter a CAPTCHA](#who-might-encounter-a-captcha)
6. [FAQ](#frequently-asked-questions)
7. [See Also](#see-also)

## Overview

CAPTCHA is used to help protect the service from automated traffic, abuse, and other unwanted activity. While CAPTCHA could be shown on every user interaction, doing so would interrupt normal user flow and negatively affect the overall experience.

To balance security and usability, the service does not display CAPTCHA for every request. Instead, a challenge appears only when the system detects suspicious behavior or unusual traffic patterns.

---

## How CAPTCHA Is Triggered

The system continuously evaluates incoming requests and overall traffic patterns. A CAPTCHA may be triggered when a request or a group of requests differs from what is considered normal behavior.

CAPTCHA can also be enabled manually when additional protection is needed.

> **Placeholder:** Flowchart illustrating request evaluation → Rule check → CAPTCHA challenge or request allowed

This approach helps protect the service without affecting most users.

---

## Conditions for Triggering CAPTCHA

Each condition listed below is evaluated independently.  
If **any** of the conditions is met, a CAPTCHA challenge will be presented to the user.

### 1. High number of requests from one IP address

A CAPTCHA is triggered if more than **500 requests** are received from the same IP address within **20 minutes**.

This behavior often indicates automated scripts or bots sending requests much faster than a human user would.

An example of this could be a bot attempting to scrape data or perform a brute-force attack.

---

### 2. IP address is blacklisted

A CAPTCHA is shown if a request comes from an IP address that is present on the service’s blacklist.

Blacklisted IP addresses are typically associated with suspicious or previously abusive activity.

An example of this could be an IP address that has been reported for sending spam or attempting to exploit vulnerabilities.

> **Placeholder:** Link to IP blacklist management documentation

---

### 3. Traffic spike compared to normal usage

A CAPTCHA may be triggered if the number of requests in the **current hour** exceeds **twice the average** number of requests for the same hour over the **previous two weeks**.

This condition helps protect the service during sudden traffic spikes that may indicate coordinated attacks or abnormal behavior.

An example of this could be a sudden surge in traffic from a specific region or during a particular time of day.

> **Placeholder:** Link to traffic monitoring and analytics documentation

---

### 4. Repeated identical payloads

A CAPTCHA is triggered if the same request payload is sent more than **five times within 30 seconds**.

This pattern is common in spam attempts or automated retries that repeatedly submit identical data.

An example of this could be multiple form submissions with the same content in a short period.

---

### 5. CAPTCHA enabled manually by administrators

Administrators can manually enable CAPTCHA through the admin panel for selected requests or scenarios.

This option is typically used during:

- Active attacks or abuse not yet covered by automated rules
- Maintenance periods that require additional protection

> **Placeholder:** Screenshot of admin panel with CAPTCHA settings highlighted
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

## Frequently Asked Questions

**Does seeing a CAPTCHA mean a user is blocked?**  
No. CAPTCHA is a challenge to verify that the user is human. It does not block access but may require additional steps to continue.

**Can legitimate users see CAPTCHA?**  
Yes. Shared networks, VPNs, or temporary spikes in traffic can cause legitimate users to encounter CAPTCHA. It is designed to be a temporary measure.

**How long does CAPTCHA remain active?**  
CAPTCHA typically stops appearing once traffic returns to normal patterns.

---

## See Also

- [What is CAPTCHA?](#placeholder)
- [Accessing the admin panel](#placeholder)
- [Security and abuse prevention overview](#placeholder)
- [Traffic monitoring and analytics](#placeholder)
- [IP blacklist management](#placeholder)

---
