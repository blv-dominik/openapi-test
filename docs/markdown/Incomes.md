Use the Incomes endpoint to gather insights on an account's income sources for the past 365 days. The endpoint is particularly useful when you want to verify a person's income.

<div style="background-color:#f4f6f8; border-left: 6px solid #0663F9;padding: 12px;margin-left: 25px; border-radius: 4px; margin-right: 25px">
    <strong>Info: </strong> The incomes resource is <b>only</b> available for Checking and Savings
accounts associated with banking links.
 </div>


 ### **🔦 Filterable fields**

Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.

| Field        | Available Filters                 |
| ------------ | --------------------------------- |
| `account`    | `=`, `in`                         |
| `created_at` | `gt`, `gte`, `lt`, `lte`, `range` |
| `id`         | `=`, `in`                         |

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