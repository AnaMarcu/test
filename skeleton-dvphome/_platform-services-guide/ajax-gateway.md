---
title: AJAX Gateway
breadcrumb: AJAX Gateway
header: AJAX Gateway
---

* TOC Placeholder
{:toc}

---

## Overview

The AJAX gateway is TODO blah blah blah

## Concurrent connections and timeouts

The system limits the number of AJAX requests it accepts from a single user.  These are typically in same throttle as the requests coming from the application UI:

- Aggregate: 900 requests in any 18 second period and 1800 requests in a 60 second period.
- Parallel: 100 requests.

**Note:** Limits are subject to change without notice in order to maintain optimal performance.
{: .alert .alert-info }
