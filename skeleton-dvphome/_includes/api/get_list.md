| start | Optional | integer | Start at item, zero-based integer |
| maxitems | Optional | integer | Max items to return |
| showprivate | Optional | boolean | Show entity private records if running this at top level. Use either `true` or `false`. (Default: `false`) |
| filter | Optonal | object | Filter(s) to use in list |
| sorts | Optional | `sortfield`[] | Field(s) to sort by in response |
| fields | Optional | `field`[] | Field(s) to return in response |

`filter`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| logical | Optional | object | Logical filter. Required if not using `expression`. |
| expression | Optional | object | Expression filter. Required if not using `logical`. |

`logical`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| logical_operator | Required | string | Operator. Use either `and` or `or`. |
| object | Optional | string | Object of operator |
| Logical Filter/Expression | Required | array[`logical`, `expression`] | Additional logical objects or expressions to filter by |

`expression`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| field | Required | string | Field |
| operator | Required | string | Operator |
| value | Required | string | Value. Use either `=`, `!=`, `<`, `<=`, `>=`, `>`, `like` or `is null`. |

`sortfield`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| order | Required | string | Sort by order. Use either `asc` or `desc`. |
