---
title: API Reference
layout: default
breadcrumb: API
header: API Reference
---

* TOC Placeholder
{:toc}

---

## About Legacy Functions
{:.no_toc}

About legacy functions!

---

{% for section in site.data.api-sections %}
## {{ section.title }}

{{ section.description }}
{: .lead }

{% for doc in site.api %}
{% if doc.url contains section.baseurl and doc.url != section.baseurl %}- [{{ doc.title }}]({{ doc.url | prepend:site.baseurl }}){% endif %}{% endfor %}
{% endfor %}
