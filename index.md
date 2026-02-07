# How and When CAPTCHAs are Displayed

## Overview

CAPTCHA is used to help protect the service from automated traffic, abuse, and other unwanted activity. While CAPTCHA can be shown on every user interaction, doing so can interrupt normal user flow and negatively affect the overall experience.

To balance security and usability, our service does not show a CAPTCHA to every user. Instead, it appears only when the system notices suspicious behavior or sudden spikes in traffic.

> **See Also**
>
> - [What is CAPTCHA?](#what-is-captcha)
> - [CAPTCHA implementation details](#captcha-implementation-details)

---

## When a CAPTCHA Is Shown

CAPTCHA is shown if **any** of the following conditions are met.

### 1. High Number of Requests from One IP Address

More than **500 requests** are received from the same IP address within **20 minutes**.

This usually indicates automated behavior, such as scripts or bots sending many requests in a short period of time.

### 2. IP address is blacklisted

The request originates from an IP address that is present in the blacklist.

> **Placeholder:** Link to IP blacklist management documentation

### 3. Traffic spike compared to baseline

The number of requests in the **current hour** exceeds **twice** the average number of requests for the same hour over the **previous two weeks**.

> **Placeholder:** Link to traffic monitoring documentation

### 4. Repeated identical payload

The same request payload is sent more than **five times within 30 seconds**. This can indicate automated scripts or bots trying to perform the same action repeatedly.

### 5. CAPTCHA enabled manually

CAPTCHA is enabled manually through the admin panel for specific requests. This allows administrators to proactively protect against suspicious activity or during periods of increased risk.

---

## What Happens When CAPTCHA Is Triggered?

When a CAPTCHA is triggered:

- The user is presented with a CAPTCHA challenge that they must solve to proceed.
- If the user successfully solves the CAPTCHA, they can continue with their request as normal.
- If the user fails to solve the CAPTCHA, they will be prompted to try again until they succeed or choose to abandon the request.
