Belvo's Recurring Expenses API allows you to identify a user's regular payments for subscription services, such as Netflix or gym memberships, as well as utility payments, such as electricity or phone bills. We return information for up to 365 days.

<div style="background-color:#f4f6f8; border-left: 6px solid #0663F9;padding: 12px;margin-left: 25px; border-radius: 4px; margin-right: 25px">
    <strong>Info: </strong> The recurring expenses resource is <b>only</b> available for Checking and Savings accounts associated with banking links.
 </div>

 ### **🔦 Filterable fields**

Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.

| Field     | Available Filters |
| --------- | ----------------- |
| `account` | `=`, `in`         |
| `id`      | `=`, `in`         |
| `link`    | `=`, `in`         |

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