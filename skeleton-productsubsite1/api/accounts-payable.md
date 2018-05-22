---
title: Accounts Payable
layout: default
permalink: /api/accounts-payable/
---

{% for section in site.data.api-sections %}
{% if page.title == section.title %}
{{ section.description }}
{: .lead }

{% for doc in site.api %}
{% if doc.url contains section.baseurl and doc.url != section.baseurl %}- [{{ doc.title }}]({{ doc.url | prepend:site.baseurl }}){% endif %}{% endfor %}
{% endif %}
{% endfor %}
