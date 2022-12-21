# Filterable fields per enddpoint

## Links

### **🔦 Filterable fields**

Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.

| Field                 | Available Filters                 |
| --------------------- | --------------------------------- |
| `access_mode`         | `=`                               |
| `created_at `         | `gt`, `gte`, `lt`, `lte`, `range` |
| `created_by`          | `not_in`                          |
| `external_id`         | `=`, `in`                         |
| `id`                  | `=`, `in`                         |
| `institution`         | `=`, `in`                         |
| `institution_user_id` | `=`, `in`                         |
| `refresh_rate`        | `=`                               |
| `status`              | `=`, `in`                         |

```curl cURL
# Filtering results to have links just from two institutions
https://sandbox.belvo.com/api/links/?institution__in=erebor_mx_retail,gringotts_mx_retail 

# Filtering results from one institution and a certain status
https://sandbox.belvo.com/api/links/?institution__in=erebor_mx_retail,gringotts_mx_retail&status=invalid
```
```javascript Node
//  Filtering results to have links just from two institutions
client.links.list({
  filters: {
    institution__in: "erebor_mx_retail,gringotts_mx_retail"
  }
})

//  Filtering results from one institution and a certain status

client.links.list({
  filters: {
    institution__in: "erebor_mx_retail,gringotts_mx_retail",
    status="invalid"
  }
})
```
```python Python
# Filtering results to have links just from two institutions
client.Links.list(institution__in="erebor_mx_retail,gringotts_mx_retail")

# Filtering results from one institution and a certain status
client.Links.list(institution__in="erebor_mx_retail,gringotts_mx_retail", status="invalid")
```
```ruby Ruby
# Filtering results so that you get institutions from just one country:
client.institutions.list(params: {
  country_code: "br"
})

# Filtering results so that you get institutions from just one country and from retail institution:
client.institutions.list(params: {
  country_code: "br",
  type__in: "retail"
})
```

## Institutions

### **🔦 Filterable fields**

Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.


|Field| Available Filters|
|---|---|
|`code`|`=`, `in`|
|`country_code`|`=`, `in`|
|`display_name`|`=`|
|`name`|`=`, `in`|
|`resources`|`allin`|
|`status`|`=`, `in`|
|`type`|`=`, `in`|
|`website`|`=`|

[block:callout]
{
  "type": "info",
  "title": "Support for partial display_name searches",
  "body": "When filtering by `display_name`, our API supports partial searches of at least one character in length. For example, if you use `display_name=Banco`, we'll return Banco Bradesco, Banco do Brasil, Bancolombia, Banco de Bogotá, Banco Falabella, Hey Banco, and so on."
}
[/block]
```curl cURL
# Filtering results so that you get institutions from just one country:
ttps://sandbox.belvo.com/api/institutions/?country_code=br

# Filtering results so that you get institutions from just one country and from retail institutions:
ttps://sandbox.belvo.com/api/institutions/?country_code=br&type__in=retail
```
```javascript Node
//  Filtering results so that you get institutions from just one country:
client.institutions.list({
  filters: {
    country_code: "br"
  }
})

//  Filtering results so that you get institutions from just one country and from retail institutions:

client.institutions.list({
  filters: {
    country_code: "br",
    type__in="retail"
  }
})
```
```python Python
# Filtering results so that you get institutions from just one country:
client.Institutions.list(country_code="br")

# Filtering results so that you get institutions from just one country and from retail institutions:
client.Institutions.list(country_code="br", type__in="retail")
```
```ruby Ruby
# Filtering results so that you get institutions from just one country:
client.institutions.list(params: {
  country_code: "br"
})

# Filtering results so that you get institutions from just one country and from retail institutions:
client.institutions.list(params: {
  country_code: "br",
  type__in: "retail"
})
```

## Accounts

> 🚧 Scheduled field deprecation
> 
> Please note that we will soon be deprecating the following fields in our `loan_data` object:
> 
> - `cutting_date`
> - `cutting_day`
> - `credit_limit`: replaced by the `principal` field.
> - `interest_rate`: replaced by the `interest_rates` object.
> - `last_payment_date`
> - `last_period_balance`: replaced by the `outstanding_balance ` field.
> - `limit_day`
> - `limit_date`: replaced by the `payment_day ` field.
> - `no_interest_payment`
> - `payment_due_day`

### **🔦 Filterable fields**

Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.

| Field                         | Available Filters                      |
| ----------------------------- | -------------------------------------- |
| `balance__available`          | `=`, `gt`, `gte`, `lt`, `lte`, `range` |
| `balance__current`            | `=`, `gt`, `gte`, `lt`, `lte`, `range` |
| `bank_product_id`             | `=`                                    |
| `category`                    | `=`, `in`                              |
| `created_at `                 | `gt`, `gte`, `lt`, `lte`, `range`      |
| `currency`                    | `=`\*, `in`                            |
| `id`                          | `=`, `in`                              |
| `institution`                 | `=`, `in`                              |
| `internal_identification`     | `=`                                    |
| `link`                        | `=`, `in`                              |
| `name`                        | `=`, `icontains`                       |
| `number`                      | `=`, `in`                              |
| `public_identification_name`  | `=`                                    |
| `public_identification_value` | `=`                                    |
| `type`                        | `=`, `in`                              |

```curl cURL
## Filtering results to have savings accounts with a balance
## between 5000 and 8000 Colombian pesos
https://sandbox.belvo.com/api/accounts/?category=savings&balance__available__range=5000,8000&currency=COP
```
```javascript Node
// Filtering results to have savings accounts with a balance
// between 5000 and 8000 Colombian pesos
client.accounts.list({
  filters: {
    category: "savings",
    balance__available__range: "5000,8000",
    currency: "COP"
  }
})
```
```python Python
## Filtering results to have savings accounts with a balance
## between 5000 and 8000 Colombian pesos
client.Accounts.list(category="savings",balance__available__range="5000,8000",currency="COP")
```
```ruby Ruby
## Filtering results to have savings accounts with a balance
## between 5000 and 8000 Colombian pesos
client.accounts.list(params: {
  category: "savings",
  balance__available__range: "5000,8000",
  currency: "COP"
})
```

## Transactions

### **🔦 Filterable fields**


Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.


|Field| Available Filters|
|---|---|
|`account`|`=`, `in`|
|`account__balance__available`|`=`, `lt`, `lte`, `range`|
|`account__balance__current`|`=`, `gt`, `gte`, `lt`, `lte`, `range`|
|`account_type`|`=`, `in`|
|`accounting_date`|`=`, `gt`, `gte`, `lt`, `lte`, `range`|
|`amount`|`=`, `gt`, `gte`, `lt`, `lte`, `range`|
|`credit_card_data__bill_name`|`=`, `in`|
|`created_at `|`gt`, `gte`, `lt`, `lte`, `range`|
|`currency`|`=`, `in`|
|`id`|`=`, `in`|
|`institution`|`=`, `in`|
|`link`|`=`, `in`|
|`reference`|`=`, `in`|
|`status`|`=`, `in`|
|`type`|`=`, `in`|
|`value_date`|`=`, `gt`, `gte`, `lt`, `lte`, `range`|

```curl cURL
# Filtering results to have transactions just from one link
https://api.belvo.com/api/transactions/?link=link_id

# Filtering results to have transactions just form one link and between a date range
https://api.belvo.com/api/transactions/?link=link_id&value_date__range=2020-10-01,2020-12-01

```
```javascript Node
// Filtering results to have transactions just from one link

client.transactions.list({
  filters: {
    link: "link_id"
  }
})

// Filtering results to have transactions just form one link and between a date range
client.transactions.list({
  filters: {
    link: "link_id",
    value_date__range: "2020-10-01,2020-12-01"
  }
})

```
```python Python
# Filtering results to have links just from two institutions
client.Transactions.list(link="link_id")

# Filtering results from one institution and a certain status
client.Transactions.list(link="link_id", value_date__range="2020-10-01,2020-12-01")

```
```ruby Ruby
# Filtering results to have links just from two institutions
client.transactions.list(params: {
  link: "link_id"
})

# Filtering results from one institution and a certain status
client.transactions.list(params: {
  link: "link_id",
  value_date__range: "2020-10-01,2020-12-01"
})
```

## Balances

### **🔦 Filterable fields**

Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.


|Field| Available Filters|
|---|---|
|`account`|`=`, `in`|
|`account_type`|`=`, `in`|
|`balance`|`=`, `gt`, `gte`, `lt`, `lte`, `range`|
|`currency`|`=`, `in`|
|`current_balance`|`=`, `gt`, `gte`, `lt`, `lte`, `range`|
|`id`|`=`, `in`|
|`institution`|`=`, `in`|
|`link`|`=`, `in`|
|`value_date`|`=`, `gt`, `gte`, `lt`, `lte`, `range`|


```curl cURL
# Filtering results to have balances greater than 5000
https://api.belvo.com/api/balances/?balance__gt=5000 

# Filtering results to have balances greater than 5000 and in Brazilian Reis
https://api.belvo.com/api/balances/?balance__gt=5000&currency=BRL
```
```javascript Node
//  Filtering results to have balances greater than 5000
client.balances.list({
  filters: {
    balance__gt: 5000
  }
})

//  Filtering results to have balances greater than 5000 and in Brazilian Reis

client.balances.list({
  filters: {
    balance__gt: 5000,
    currency: "BRL"
  }
})
```
```python Python
# Filtering results to have balances greater than 5000
client.Balances.list(balance__gt=5000)

# Filtering results to have balances greater than 5000 and in Brazilian Reis
client.Balances.list(balance__gt=5000, currency="BRL")
```
```ruby Ruby
# Filtering results to have balances greater than 5000
client.balances.list(params: {
  balance__gt: 5000
})

# Filtering results to have balances greater than 5000 and in Brazilian Reis
client.balances.list(params: {
  balance__gt: 5000,
  currency: "BRL"
})
```

## Owners

### **🔦 Filterable fields**


Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.


|Field| Available Filters|
|---|---|
|`created_at `|`gt`, `gte`, `lt`, `lte`, `range`|
|`email`|`=`|
|`id`|`=`, `in`|
|`link`|`=`, `in`|

```curl cURL
# Filtering results so that you get the emails of one link:
https://sandbox.belvo.com/api/owners/?email=filtering@belvo.com

```
```javascript Node
// Filtering results so that you get the emails of one link:
client.owners.list({
  filters: {
    email: "filtering@belvo.com"
  }
})

```
```python Python
# Filtering results so that you get the emails of one link:
client.Owners.list(email="filtering@belvo.com")

```
```ruby Ruby
# Filtering results so that you get the emails of one link:
client.owners.list(params: {
  email: "filtering@belvo.com"
})

})
```

## Investment Portfolios

### **🔦 Filterable fields**


Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.


|Field| Available Filters|
|---|---|
|`created_at `|`gt`, `gte`, `lt`, `lte`, `range`|
|`link`|`=`, `in`|

```curl cURL
# Filtering results so that you get the portfolios of one link:
https://sandbox.belvo.com/investments/portfolios/?link=89c91f42-df34-4c5d-a4f1-6e1e40438af4

```
```javascript Node
// Filtering results so that you get the portfolios of one link:
client. investmentsPortfolios.list({
  filters: {
    link: "89c91f42-df34-4c5d-a4f1-6e1e40438af4"
  }
})

```
```python Python
# Filtering results so that you get the portfolios of one link:
client. InvestmentsPortfolios.list(link="89c91f42-df34-4c5d-a4f1-6e1e40438af4")

```
```ruby Ruby
# Filtering results so that you get the portfolios of one link:
client. investments_portfolio.list(params: {
  link: "89c91f42-df34-4c5d-a4f1-6e1e40438af4"
})
```

## Incomes 

### **🔦 Filterable fields**


Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.


|Field| Available Filters|
|---|---|
|`account`|`=`, `in`|
|`created_at`|`gt`, `gte`, `lt`, `lte`, `range`|
|`id`|`=`, `in`|


```curl cURL
# Filtering results to have incomes from one link:
https://sandbox.belvo.com/api/incomes/?link=link-id

# Filtering results to have incomes from one link and from two of their accounts:
https://sandbox.belvo.com/api/incomes/?link=link-id&account__in=account-id1,account-id2
```
```javascript Node
// Filtering results to have incomes from one link:
client.incomes.list({
  filters: {
    link: "link-id"
  }
})

// Filtering results to have incomes from one link and from two of their accounts:

client.incomes.list({
  filters: {
    link: "link-id",
    account__in: "account-id1,account-id2"
  }
})
```
```python Python
# Filtering results to have incomes from one link:
client.Incomes.list(link="link-id")

# Filtering results to have incomes from one link and from two of their accounts:
client.Incomes.list(link="link-id", account__in="account-id1,account-id2")
```
```ruby Ruby
# Filtering results to have incomes from one link:
client.incomes.list(params: {
  link: "link-id"
})

# Filtering results to have incomes from one link and from two of their accounts:
client.incomes.list(params: {
  link: "link-id",
  account__in: "account-id1,account-id2"
})
```

## Recurring exepenses

### **🔦 Filterable fields**


Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.


|Field| Available Filters|
|---|---|
|`account`|`=`, `in`|
|`id`|`=`, `in`|
|`link`|`=`, `in`|

```curl cURL
# Filtering results so that you get the recurring expenses of one account:
https://sandbox.belvo.com/api/recurring-expenses/?account=89c91f42-df34-4c5d-a4f1-6e1e40438af4

```
```javascript Node
// Filtering results so that you get the recurring expenses of one account:
client. recurringExpenses.list({
  filters: {
    account: "89c91f42-df34-4c5d-a4f1-6e1e40438af4"
  }
})

```
```python Python
# Filtering results so that you get the recurring expenses of one account:
client. RecurringExpenses.list(account="89c91f42-df34-4c5d-a4f1-6e1e40438af4")

```
```ruby Ruby
# Filtering results so that you get the recurring expenses of one account:
client. recurring_expenses.list(params: {
  account: "89c91f42-df34-4c5d-a4f1-6e1e40438af4"
})
```
## Risk Insights

### **🔦 Filterable fields**


Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.


|Field| Available Filters|
|---|---|
|`id`|`=`, `in`|
|`link`|`=`, `in`|

```curl cURL
# Filtering results so that you get the risk insights of one link:
https://sandbox.belvo.com/api/risk-insights/?link=89c91f42-df34-4c5d-a4f1-6e1e40438af4

```
```javascript Node
// Filtering results so that you get the risk insights of one link:
client. riskInsights.list({
  filters: {
    account: "89c91f42-df34-4c5d-a4f1-6e1e40438af4"
  }
})

```
```python Python
# Filtering results so that you get the risk insights of one link:
client. RiskInsights.list(link="89c91f42-df34-4c5d-a4f1-6e1e40438af4")

```
```ruby Ruby
# Filtering results so that you get the risk insights of one link:
client. risk_insights.list(params: {
  link: "89c91f42-df34-4c5d-a4f1-6e1e40438af4"
})
```

## Invoices

### **🔦 Filterable fields**


Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.

|Field| Available Filters|
|---|---|
|`created_at `|`gt`, `gte`, `lt`, `lte`, `range`|
|`id`|`=`, `in`|
|`invoice_date`|`=`, `gt`, `gte`, `lt`, `lte`, `range`|
|`invoice_identification`|`=`, `gt`, `gte`, `lt`, `lte`, `range`|
|`link`|`=`, `in`|
|`status`|`=`, `in`|
|`total_amount`|`=`, `gt`, `gte`, `lt`, `lte`, `range`|
|`type`|`=`, `in`|

```curl cURL
# Filtering results so that you get Tax Returns from one link:
https://sandbox.belvo.com/api/invoices/?link=link-id

# Filtering results so that you get Tax Returns from two links 
# and are of type normal and their status is vigente:
https://sandbox.belvo.com/api/invoices/?link__in=link-id1,link-id2&informacion_general__tipo_declaracion=Normal&status=vigente
```
```javascript Node
//  Filtering results so that you get the Tax Returns from one link:
client.invoices.list({
  filters: {
    link: "link-id"
  }
})

//  Filtering results so that you get the Tax Returns from two links
// and are of type normal and their status is vigente:
client.invoices.list({
  filters: {
    link__in: "link-id-1, link-id-2",
    informacion_general__tipo_declaracion: "Normal",
    status: "vigente"
  }
})

```
```python Python
# Filtering results so that you get the Tax Return from one link:
client.invoices.list(link="link-id")

# Filtering results so that you get the Tax Returns from two links
# # and are of type normal and their status is vigente:
client.invoices.list(link__in="link-id1,link-id2", informacion_general__tipo_declaracion="Normal", status="vigente")
```
```ruby Ruby
# Filtering results so that you get the Tax Return from one link:
client.invoices.list(params: {
  link: "link-id"
})


# Filtering results so that you get the Tax Returns from two links
# and are of type normal and their status is vigente:
client.invoices.list(params: {
  link__in: "link-id1, link-id1",
  informacion_general__tipo_declaracion: "Normal",
  status: "vigente"
})
```

## Tax Returns


### **🔦 Filterable fields**


|Field| Available Filters|
|---|---|
|`created_at `|`gt`, `gte`, `lt`, `lte`, `range`|
|`id`|`=`, `in`|
|`informacion_general__ejercicio`|`=`, `gt`, `gte`, `lt`, `lte`, `range`|
|`informacion_general__tipo_declaracion`|`=`, `in`|
|`link`|`=`, `in`|



```curl cURL
# Filtering results so that you get Tax Returns from one link:
https://api.belvo.com/api/tax-returns/?link=link-id

# Filtering results so that you get Tax Returns from two links and are of type normal:
https://api.belvo.com/api/tax-returns/?link__in=link-id1,link-id2&informacion_general__tipo_declaracion=Normal,
```
```javascript Node
//  Filtering results so that you get the Tax Returns from one link:
client.taxReturns.list({
  filters: {
    link: "link-id"
  }
})

//  Filtering results so that you get the Tax Returns from two links and are of type normal:
client.taxReturns.list({
  filters: {
    link__in: "link-id-1, link-id-2",
    informacion_general__tipo_declaracion: "Normal"
  }
})

```
```python Python
# Filtering results so that you get the Tax Return from one link:
client.TaxReturns.list(link="link-id")

# Filtering results so that you get the Tax Returns from two links and are of type normal:
client.TaxReturns.list(link__in="link-id1,link-id2", informacion_general__tipo_declaracion: "Normal")
```
```ruby Ruby
# Filtering results so that you get the Tax Return from one link:
client.tax_returns.list(params: {
  link: "link-id"
})


# Filtering results so that you get the Tax Returns from two links and are of type normal:
client.tax_returns.list(params: {
  link__in: "link-id1, link-id1",
  informacion_general__tipo_declaracion: "Normal"
})
```

## Tax Status

### **🔦 Filterable fields**


Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.

|Field| Available Filters|
|---|---|
|`created_at `|`gt`, `gte`, `lt`, `lte`, `range`|
|`id`|`=`, `in`|
|`link`|`=`, `in`|

```curl cURL
# Filtering results so that you get institutions from just one link:
https://api.belvo.com/api/institutions/?link=link
```
```javascript Node
//  Filtering results so that you get institutions from just one link:
client.taxstatus.list({
  filters: {
    link: "link_id"
  }
})

```
```python Python
# Filtering results so that you get institutions from just one link:
client.TaxStatus.list(link="link")
```
```ruby Ruby
# Filtering results so that you get institutions from just one link:
client.tax_status.list(params: {
  link: "link"
})
```

## Tax Compliance Status

### **🔦 Filterable fields**


Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.

|Field| Available Filters|
|---|---|
|`created_at `|`gt`, `gte`, `lt`, `lte`, `range`|
|`id`|`=`, `in`|
|`link`|`=`, `in`|


```curl cURL
# Filtering results so that you get Tax Compliance Status from one link:
https://api.belvo.com/api/tax-compliance-status/?link=link-id

# Filtering results so that you get Tax Compliance Status from one link:
https://api.belvo.com/api/tax-compliance-status/?link=link-id1,link-id2
```
```javascript Node
//  Filtering results so that you get the Tax Compliance Status from one link:
client.taxComplianceStatus.list({
  filters: {
    link: "link-id"
  }
})

//  Filtering results so that you get the Tax Compliance Status from two links:
client.taxComplianceStatus.list({
  filters: {
    link__in: "link-id-1, link-id-2"
  }
})

```
```python Python
# Filtering results so that you get the Tax Compliance Status from one link:
client.TaxComplianceStatus.list(link="link-id")

# Filtering results so that you get the Tax Compliance Status from two links:
client.TaxComplianceStatus.list(link__in="link-id1,link-id2")
```
```ruby Ruby
# Filtering results so that you get the Tax Compliance Status from one link:
client.tax_compliance_status.list(params: {
  link: "link-id"
})


# Filtering results so that you get the Tax Compliance Status from two link:
client.tax_compliance_status.list(params: {
  link__in: "link-id1, link-id1"
})
```

## Tax Retentions

### **🔦 Filterable fields**


Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.

|Field| Available Filters|
|---|---|
|`created_at `|`gt`, `gte`, `lt`, `lte`, `range`|
|`link`|`=`, `in`|

```curl cURL
# Filtering results so that you get Tax Retentions from one link:
https://sandbox.belvo.com/api/tax-retentions/?link=link-id

# Filtering results so that you get Tax Retentions from two links 
https://api.belvo.com/api/tax-retentions/?link=link-id1,link-id2
```
```javascript Node
//  Filtering results so that you get the Tax Retentions from one link:
client.taxRetentions.list({
  filters: {
    link: "link-id"
  }
})

//  Filtering results so that you get the Tax Retentions from two links:
client.taxRetentions.list({
  filters: {
    link__in: "link-id-1, link-id-2"
  }
})

```
```python Python
# Filtering results so that you get the Tax Retentions from one link:
client.TaxRetentions.list(link="link-id")

# Filtering results so that you get the Tax Retentions from two links:
client.TaxRetentions.list(link__in="link-id1,link-id2")
```
```ruby Ruby
# Filtering results so that you get the Tax Retentions from one link:
client.tax_retentions.list(params: {
  link: "link-id"
})


# Filtering results so that you get the Tax Retentions from two link:
client.tax_retentions.list(params: {
  link__in: "link-id1, link-id1"
})
```