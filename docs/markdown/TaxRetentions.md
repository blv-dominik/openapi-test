A **tax retention** is the amount of money that the payer must deduct from the total amount of a purchase invoice, according to the fiscal institution’s regulations.

With Belvo’s Tax Retentions resource, you can quickly and easily consult information regarding a user’s tax retentions over a given period or for a specific invoice. This is particularly useful when you want to aid your user in their tax returns as for each invoice you receive the:

- invoice amount
- amount that is exempt from taxation
- total amount that is taxed
- breakdown of all the taxes applied to the invoice


### **🔦 Filterable fields**

Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.

| Field         | Available Filters                 |
| ------------- | --------------------------------- |
| `created_at ` | `gt`, `gte`, `lt`, `lte`, `range` |
| `link`        | `=`, `in`                         |

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