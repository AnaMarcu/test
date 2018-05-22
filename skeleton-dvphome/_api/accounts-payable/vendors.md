---
title: Vendors
include_base: api/accounts-payable/vendors
---

* TOC Placeholder
{:toc}

---

Vendors are companies or individuals that are paid for goods and services.

---

## List Vendors

### readByQuery

{% highlight xml %}
{% include {{ page.include_base }}/readByQuery.xml %}
{% endhighlight %}

#### Parameters

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| object | Required | string | Use `VENDOR` |
| fields | Optional | string | {% include api/readByQuery-fields.md %} |
| query | Required | string | {% include api/readByQuery-query.md %} |
| pagesize | Optional | integer | {% include api/readByQuery-pagesize.md %} |

`query`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| STATUS | Optional | string | Status. Use `T` for Active and `F` for Inactive. |
| ONETIME | Optional | string | One-time use. Use `T` for one-time use or `F` otherwise. |

---

## Get Vendor

### read

{% highlight xml %}
{% include {{ page.include_base }}/read.xml %}
{% endhighlight %}

#### Parameters

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| object | Required | string | Use `VENDOR` |
| keys | Required | string | Vendor `RECORDNO` to get | 
| fields | Optional | string | {% include api/read-fields.md %} | 

---

## Get Vendor by Name

### readByName

{% highlight xml %}
{% include {{ page.include_base }}/readByName.xml %}
{% endhighlight %}

#### Parameters

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| object | Required | string | Use `VENDOR` |
| keys | Required | string | Vendor `VENDORID` to get |
| fields | Optional | string | {% include api/read-fields.md %} |

---

## Create Vendor

### create

{% highlight xml %}
{% include {{ page.include_base }}/create.xml %}
{% endhighlight %}

#### Parameters

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| VENDOR | Optional | object | Object to create |


`VENDOR`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| VENDORID | Optional | string | Vendor `VENDORID` to create. Required if company does not use auto-numbering. |
| NAME | Required | string | Name |
| DISPLAYCONTACT | Required | object | Contact info |
| STATUS | Optional | string | Status. Use `active` for Active or `inactive` for Inactive (Default: `active`) |
| ONETIME | Optional | boolean | One time. Use `false` for No, `true` for Yes. (Default: `false`) |
| HIDEDISPLAYCONTACT | Optional | boolean | Exclude from contact list. Use `false` for No, `true` for Yes. (Default: `false`) |
| VENDTYPE | Optional | string | Vendor type ID |
| PARENTID | Optional | string | Parent vendor ID |
| GLGROUP | Optional | string | GL group name |
| TAXID | Optional | string | Tax ID |
| NAME1099 | Optional | string | Form 1099 name |
| FORM1099TYPE | Optional | string | Form 1099 type |
| FORM1099BOX | Optional | string | Form 1099 box |
| SUPDOCID | Optional | string | Attachments ID |
| APACCOUNT | Optional | string | Default expense GL account number |
| OFFSETGLACCOUNTNO | Optional | string | AP account number |
| CREDITLIMIT | Optional | currency | Credit limit |
| ONHOLD | Optional | boolean | On hold. Use `false` for No, `true` for Yes. (Default: `false`) |
| DONOTCUTCHECK | Optional | boolean | Do not pay. Use `false` for No, `true` for Yes. (Default: `false`) |
| COMMENTS | Optional | string | Comments |
| CURRENCY | Optional | string | Default currency code |
| CONTACTINFO | Optional | object | Primary contact. If blank system will use DISPLAYCONTACT. |
| PAYTO | Optional | object | Pay to contact. If blank system will use DISPLAYCONTACT. |
| RETURNTO | Optional | object | Return to contact. If blank system will use DISPLAYCONTACT. |
| PAYMETHODKEY | Optional | string | Preferred payment method |
| MERGEPAYMENTREQ | Optional | boolean | Merge payment requests. Use `false` for No, `true` for Yes. (Default: `true`) |
| PAYMENTNOTIFY | Optional | boolean | Send automatic payment notification. Use `false` for No, `true` for Yes. (Default: `false`) |
| BILLINGTYPE | Optional | string | Vendor billing type |
| PAYMENTPRIORITY | Optional | string | Payment priority |
| TERMNAME | Optional | string | Payment term |
| DISPLAYTERMDISCOUNT | Optional | boolean | Display term discount on check stub. Use `false` for No, `true` for Yes. (Default: `true`) |
| ACHENABLED | Optional | boolean | ACH enabled. Use `false` for No, `true` for Yes. (Default: `false`) |
| ACHBANKROUTINGNUMBER | Optional | string | ACH bank routing number |
| ACHACCOUNTNUMBER | Optional | string | ACH bank account number |
| ACHACCOUNTTYPE | Optional | string | ACH bank account type |
| ACHREMITTANCETYPE | Optional | string | ACH bank account class |
| VENDORACCOUNTNO | Optional | string | Vendor account number |
| DISPLAYACCTNOCHECK | Optional | boolean | Display location assigned account number on check stub. Use `false` for No, `true` for Yes. (Default: `false`) |
| OBJECTRESTRICTION | Optional | string | Restriction type. Use `Unrestricted`, `RootOnly`, or `Restricted`. (Default `Unrestricted`) |
| RESTRICTEDLOCATIONS | Optional | string | Restricted location ID's. Use if OBJECTRESTRICTION is `Restricted`. Implode multiple ID's with `#~#`. |
| RESTRICTEDDEPARTMENTS | Optional | string | Restricted department ID's. Use if OBJECTRESTRICTION is `Restricted`. Implode multiple ID's with `#~#`. |
| Custom fields | Optional | varies | This object supports custom fields. |

`DISPLAYCONTACT`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| PRINTAS | Required | string | Print as |
| CONTACTNAME | Optional | string | If left blank, system will create the name as `[NAME](V[VENDORID])` |
| COMPANYNAME | Optional | string | Company name |
| TAXABLE | Optional | boolean | Taxable. Use `false` for No, `true` for Yes. (Default: `true`) |
| TAXGROUP | Optional | string | Contact tax group name |
| PREFIX | Optional | string | Prefix |
| FIRSTNAME | Optional | string | First name |
| LASTNAME | Optional | string | Last name |
| INITIAL | Optional | string | Middle name |
| PHONE1 | Optional | string | Primary phone number |
| PHONE2 | Optional | string | Secondary phone number |
| CELLPHONE | Optional | string | Cellular phone number |
| PAGER | Optional | string | Pager number |
| FAX | Optional | string | Fax number |
| EMAIL1 | Optional | string | Primary email address |
| EMAIL2 | Optional | string | Secondary email address |
| URL1 | Optional | string | Primary URL |
| URL2 | Optional | string | Secondary URL |
| MAILADDRESS | Optional | object | Mail address |

`MAILADDRESS`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| ADDRESS1 | Optional | string | Address line 1 |
| ADDRESS2 | Optional | string | Address line 2 |
| CITY | Optional | string | City |
| STATE | Optional | string | State/province |
| ZIP | Optional | string | Zip/postal code |
| COUNTRY | Optional | string | Country |


`CONTACTINFO`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| CONTACTNAME | Required | string | Primary contact name |


`PAYTO`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| CONTACTNAME | Required | string | Pay to contact name |


`RETURNTO`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| CONTACTNAME | Required | string | Return to contact name |

---

## Create Vendor (Legacy)

### create_vendor

{% highlight xml %}
{% include {{ page.include_base }}/create_vendor.xml %}
{% endhighlight %}

#### Parameters

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| vendorid | Required | string | Vendor ID to create. Leave blank if company uses auto-numbering. |
| name | Required | string | Name |
| parentid | Optional | string | Parent vendor ID |
| termname | Optional | string | Payment term |
| glaccountno | Optional | string | Default expense GL account number |
| vendtype | Optional | string | Vendor type ID |
| taxid | Optional | string | Tax ID |
| creditlimit | Optional | currency | Credit limit |
| paymethod | Optional | string | Preferred payment method |
| billingtype | Optional | string | Vendor billing type |
| vendoraccountno | Optional | string | Vendor account number |
| displocacctnocheck | Optional | boolean | Display location assigned account number on check stub. Use `false` for No, `true` for Yes. (Default: `false`) |
| onhold | Optional | boolean | On hold. Use `false` for No, `true` for Yes. (Default: `false`) |
| donotcutcheck | Optional | boolean | Do not pay. Use `false` for No, `true` for Yes. (Default: `false`) |
| comments | Optional | string | Comments |
| status | Optional | string | Status. Use `active` for Active or `inactive` for Inactive (Default: `active`) |
| currency | Optional | string | Default currency code |
| onetime | Optional | boolean | One time. Use `false` for No, `true` for Yes. (Default: `false`) |
| primary | Optional | object | Primary contact. If blank system will use the corresponding `contactinfo`. |
| returnto | Optional | object | Return to contact. If blank system will use the corresponding `contactinfo`. |
| payto | Optional | object | Pay to contact. If blank system will use the corresponding `contactinfo`. |
| contactinfo | Optional | object | Contact info |
| contactto1099 | Optional | object | 1099 contact. If blank system will use the corresponding `contactinfo`. |
| contactlist | Optional | `contactitem`[] | Contact list |
| name1099 | Optional | string | Form 1099 name |
| form1099type | Optional | string | Form 1099 type |
| form1099box | Optional | string | Form 1099 box |
| customfields | Optional | `customfield`[] | Custom fields |
| paymentnotify | Optional | boolean | Send automatic payment notification. Use `false` for No, `true` for Yes. (Default: `false`) |
| achenabled | Optional | boolean | ACH enabled. Use `false` for No, `true` for Yes. (Default: `false`) |
| achbankroutingnumber | Optional | string | ACH bank routing number. |
| achaccountnumber | Optional | string | ACH bank account number. |
| achaccounttype | Optional | string | ACH bank account type. |
| achremittancetype | Optional | string | ACH bank account class. |
| displaytermdiscount | Optional | boolean | Display term discount on check stub. Use `false` for No, `true` for Yes. (Default: `true`) |
| visibility | Optional | object | Restrictions |
| supdocid | Optional | string | Attachments ID |
| mergepaymentreq | Optional | boolean | Merge payment requests. Use `false` for No, `true` for Yes. (Default: `true`) |
| offsetglaccountno | Optional | string | AP account number |

`primary`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| contactname | Required | string | Contact name of an existing contact |

`returnto`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| contactname | Required | string | Contact name of an existing contact |

`payto`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| contactname | Required | string | Contact name of an existing contact |

`contactinfo`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| contact | Required | object | New contact to create corresponding with the vendor |

`contact`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| contactname | Required | string | Contact name |
| printas | Required | string | Print as |
| taxable | Optional | boolean | Taxable. Use `false` for No, `true` for Yes. (Default: `true`) |
| companyname | Optional | string | Company name |
| taxgroup | Optional | string | Contact tax group name |
| prefix | Optional | string | Prefix |
| firstname | Optional | string | First name |
| lastname | Optional | string | Last name |
| initial | Optional | string | Middle name |
| phone1 | Optional | string | Primary phone number |
| phone2 | Optional | string | Secondary phone number |
| cellphone | Optional | string | Cellular phone number |
| pager | Optional | string | Pager number |
| fax | Optional | string | Fax number |
| email1 | Optional | string | Primary email address |
| email2 | Optional | string | Secondary email address |
| url1 | Optional | string | Primary URL |
| url2 | Optional | string | Secondary URL |
| status | Optional | string | Status. Use `active` for Active or `inactive` for Inactive (Default: `active`) |
| mailaddress | Optional | object | Mail address |
| taxid | Optional | string | Tax ID |

`mailaddress`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| address1 | Optional | string | Address line 1 |
| address2 | Optional | string | Address line 2 |
| city | Optional | string | City |
| state | Optional | string | State/province |
| zip | Optional | string | Zip/postal code |
| country | Optional | string | Country |
| isocountrycode | Optional | string | ISO country code |
| latitude | Optional | string | Latitude |
| longitude | Optional | string | Longitude |

`contactto1099`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| contactname | Required | string | Contact name of an existing contact |

`contactitem`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| category | Required | string | Category |
| contactname | Required | string | Contact name of an existing contact |

`visibility`

| visibility_type | Required | string | Restriction type. Use `Unrestricted`, `RootOnly`, or `Restricted`. (Default `Unrestricted`) |
| restricted_locs | Optional | `locationid`[] | Restricted location ID's |
| restricted_depts | Optional | `departmentid`[] | Restricted department ID's |

---

## Update Vendor

### update

{% highlight xml %}
{% include {{ page.include_base }}/update.xml %}
{% endhighlight %}

#### Parameters

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| VENDOR | Optional | object | Object to update |

`VENDOR`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| RECORDNO | Required | integer | Vendor `RECORDNO` to update  |
| NAME | Optional | string | Name |
| DISPLAYCONTACT | Optional | object | Contact info |
| STATUS | Optional | string | Status. Use `active` for Active or `inactive` for Inactive (Default: `active`) |
| ONETIME | Optional | boolean | One time. Use `false` for No, `true` for Yes. (Default: `false`) |
| HIDEDISPLAYCONTACT | Optional | boolean | Exclude from contact list. Use `false` for No, `true` for Yes. (Default: `false`) |
| VENDTYPE | Optional | string | Vendor type ID |
| PARENTID | Optional | string | Parent vendor ID |
| GLGROUP | Optional | string | GL group name |
| TAXID | Optional | string | Tax ID |
| NAME1099 | Optional | string | Form 1099 name |
| FORM1099TYPE | Optional | string | Form 1099 type |
| FORM1099BOX | Optional | string | Form 1099 box |
| SUPDOCID | Optional | string | Attachments ID |
| APACCOUNT | Optional | string | Default expense GL account number |
| OFFSETGLACCOUNTNO | Optional | string | AP account number |
| CREDITLIMIT | Optional | currency | Credit limit |
| ONHOLD | Optional | boolean | On hold. Use `false` for No, `true` for Yes. (Default: `false`) |
| DONOTCUTCHECK | Optional | boolean | Do not pay. Use `false` for No, `true` for Yes. (Default: `false`) |
| COMMENTS | Optional | string | Comments |
| CURRENCY | Optional | string | Default currency code |
| CONTACTINFO | Optional | object | Primary contact. If blank system will use DISPLAYCONTACT. |
| PAYTO | Optional | object | Pay to contact. If blank system will use DISPLAYCONTACT. |
| RETURNTO | Optional | object | Return to contact. If blank system will use DISPLAYCONTACT. |
| PAYMETHODKEY | Optional | string | Preferred payment method |
| MERGEPAYMENTREQ | Optional | boolean | Merge payment requests. Use `false` for No, `true` for Yes. (Default: `true`) |
| PAYMENTNOTIFY | Optional | boolean | Send automatic payment notification. Use `false` for No, `true` for Yes. (Default: `false`) |
| BILLINGTYPE | Optional | string | Vendor billing type |
| PAYMENTPRIORITY | Optional | string | Payment priority |
| TERMNAME | Optional | string | Payment term |
| DISPLAYTERMDISCOUNT | Optional | boolean | Display term discount on check stub. Use `false` for No, `true` for Yes. (Default: `true`) |
| ACHENABLED | Optional | boolean | ACH enabled. Use `false` for No, `true` for Yes. (Default: `false`) |
| ACHBANKROUTINGNUMBER | Optional | string | ACH bank routing number |
| ACHACCOUNTNUMBER | Optional | string | ACH bank account number |
| ACHACCOUNTTYPE | Optional | string | ACH bank account type |
| ACHREMITTANCETYPE | Optional | string | ACH bank account class |
| VENDORACCOUNTNO | Optional | string | Vendor account number |
| DISPLAYACCTNOCHECK | Optional | boolean | Display location assigned account number on check stub. Use `false` for No, `true` for Yes. (Default: `false`) |
| OBJECTRESTRICTION | Optional | string | Restriction type. Use `Unrestricted`, `RootOnly`, or `Restricted`. (Default `Unrestricted`) |
| RESTRICTEDLOCATIONS | Optional | string | Restricted location ID's. Use if OBJECTRESTRICTION is `Restricted`. Implode multiple ID's with `#~#`. |
| RESTRICTEDDEPARTMENTS | Optional | string | Restricted department ID's. Use if OBJECTRESTRICTION is `Restricted`. Implode multiple ID's with `#~#`. |
| Custom fields | Optional | varies | This object supports custom fields. |

`DISPLAYCONTACT`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| PRINTAS | Optional | string | Print as |
| COMPANYNAME | Optional | string | Company name |
| TAXABLE | Optional | boolean | Taxable. Use `false` for No, `true` for Yes. (Default: `true`) |
| TAXGROUP | Optional | string | Contact tax group name |
| PREFIX | Optional | string | Prefix |
| FIRSTNAME | Optional | string | First name |
| LASTNAME | Optional | string | Last name |
| INITIAL | Optional | string | Middle name |
| PHONE1 | Optional | string | Primary phone number |
| PHONE2 | Optional | string | Secondary phone number |
| CELLPHONE | Optional | string | Cellular phone number |
| PAGER | Optional | string | Pager number |
| FAX | Optional | string | Fax number |
| EMAIL1 | Optional | string | Primary email address |
| EMAIL2 | Optional | string | Secondary email address |
| URL1 | Optional | string | Primary URL |
| URL2 | Optional | string | Secondary URL |
| MAILADDRESS | Optional | object | Mail address |

`MAILADDRESS`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| ADDRESS1 | Optional | string | Address line 1 |
| ADDRESS2 | Optional | string | Address line 2 |
| CITY | Optional | string | City |
| STATE | Optional | string | State/province |
| ZIP | Optional | string | Zip/postal code |
| COUNTRY | Optional | string | Country |

`CONTACTINFO`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| CONTACTNAME | Required | string | Primary contact name |

`PAYTO`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| CONTACTNAME | Required | string | Pay to contact name |

`RETURNTO`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| CONTACTNAME | Required | string | Return to contact name |

---

## Update Vendor (Legacy)

### update_vendor

{% highlight xml %}
{% include {{ page.include_base }}/update_vendor.xml %}
{% endhighlight %}

#### Parameters

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| vendorid | Required | string | Vendor ID to update |
| name | Optional | string | Name |
| parentid | Optional | string | Parent vendor ID |
| termname | Optional | string | Payment term |
| glaccountno | Optional | string | Default expense GL account number |
| vendtype | Optional | string | Vendor type ID |
| taxid | Optional | string | Tax ID |
| creditlimit | Optional | currency | Credit limit |
| paymethod | Optional | string | Preferred payment method |
| billingtype | Optional | string | Vendor billing type |
| vendoraccountno | Optional | string | Vendor account number |
| displocacctnocheck | Optional | boolean | Display location assigned account number on check stub. Use `false` for No, `true` for Yes. |
| onhold | Optional | boolean | On hold. Use `false` for No, `true` for Yes. |
| donotcutcheck | Optional | boolean | Do not pay. Use `false` for No, `true` for Yes. |
| comments | Optional | string | Comments |
| status | Optional | string | Status. Use `active` for Active or `inactive` for Inactive. |
| currency | Optional | string | Default currency code |
| primary | Optional | object | Primary contact. If blank system will use the corresponding `contactinfo`. |
| returnto | Optional | object | Return to contact. If blank system will use the corresponding `contactinfo`. |
| payto | Optional | object | Pay to contact. If blank system will use the corresponding `contactinfo`. |
| contactinfo | Optional | object | Contact info |
| contactto1099 | Optional | object | 1099 contact. If blank system will use the corresponding `contactinfo`. |
| contactlist | Optional | `contactitem`[] | Contact list |
| name1099 | Optional | string | Form 1099 name |
| form1099type | Optional | string | Form 1099 type |
| form1099box | Optional | string | Form 1099 box |
| customfields | Optional | `customfield`[] | Custom fields |
| paymentnotify | Optional | boolean | Send automatic payment notification. Use `false` for No, `true` for Yes. |
| achenabled | Optional | boolean | ACH enabled. Use `false` for No, `true` for Yes. |
| achbankroutingnumber | Optional | string | ACH bank routing number. |
| achaccountnumber | Optional | string | ACH bank account number. |
| achaccounttype | Optional | string | ACH bank account type. |
| achremittancetype | Optional | string | ACH bank account class. |
| displaytermdiscount | Optional | boolean | Display term discount on check stub. Use `false` for No, `true` for Yes. |
| visibility | Optional | object | Restrictions |
| supdocid | Optional | string | Attachments ID |
| mergepaymentreq | Optional | boolean | Merge payment requests. Use `false` for No, `true` for Yes. |
| offsetglaccountno | Optional | string | AP account number |

`primary`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| contactname | Required | string | Contact name of an existing contact |

`returnto`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| contactname | Required | string | Contact name of an existing contact |

`payto`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| contactname | Required | string | Contact name of an existing contact |

`contactinfo`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| contact | Required | object | New contact to create corresponding with the vendor |

`contact`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| contactname | Required | string | Contact name |
| printas | Required | string | Print as |
| taxable | Optional | boolean | Taxable. Use `false` for No, `true` for Yes. (Default: `true`) |
| companyname | Optional | string | Company name |
| taxgroup | Optional | string | Contact tax group name |
| prefix | Optional | string | Prefix |
| firstname | Optional | string | First name |
| lastname | Optional | string | Last name |
| initial | Optional | string | Middle name |
| phone1 | Optional | string | Primary phone number |
| phone2 | Optional | string | Secondary phone number |
| cellphone | Optional | string | Cellular phone number |
| pager | Optional | string | Pager number |
| fax | Optional | string | Fax number |
| email1 | Optional | string | Primary email address |
| email2 | Optional | string | Secondary email address |
| url1 | Optional | string | Primary URL |
| url2 | Optional | string | Secondary URL |
| status | Optional | string | Status. Use `active` for Active or `inactive` for Inactive (Default: `active`) |
| mailaddress | Optional | object | Mail address |
| taxid | Optional | string | Tax ID |

`mailaddress`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| address1 | Optional | string | Address line 1 |
| address2 | Optional | string | Address line 2 |
| city | Optional | string | City |
| state | Optional | string | State/province |
| zip | Optional | string | Zip/postal code |
| country | Optional | string | Country |
| isocountrycode | Optional | string | ISO country code |
| latitude | Optional | string | Latitude |
| longitude | Optional | string | Longitude |

`contactto1099`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| contactname | Required | string | Contact name of an existing contact |

`contactitem`

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| category | Required | string | Category |
| contactname | Required | string | Contact name of an existing contact |

`visibility`

| visibility_type | Required | string | Restriction type. Use `Unrestricted`, `RootOnly`, or `Restricted`. (Default `Unrestricted`) |
| restricted_locs | Optional | `locationid`[] | Restricted location ID's |
| restricted_depts | Optional | `departmentid`[] | Restricted department ID's |

---

## Delete Vendor

### delete

{% highlight xml %}
{% include {{ page.include_base }}/delete.xml %}
{% endhighlight %}

#### Parameters

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| object | Required | string | Use `VENDOR` |
| keys | Required | string | Vendor `RECORDNO` to delete |

---

## Delete Vendor (Legacy)

### delete_vendor

{% highlight xml %}
{% include {{ page.include_base }}/delete_vendor.xml %}
{% endhighlight %}

#### Parameters

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| vendorid | Required | string | Vendor ID to delete |

---

## Create Location Specific Vendor Account Number (Legacy)

### create_vendorentityaccountno

{% highlight xml %}
{% include {{ page.include_base }}/create_vendorentityaccountno.xml %}
{% endhighlight %}

#### Parameters

| Name | Required | Type | Description |
| --- | --- | --- | --- |
| vendorid | Required | string | Vendor ID |
| accountno | Required | string | Vendor account number |
| locationid | Required | string | Location ID |

---
