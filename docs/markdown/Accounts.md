An **account** is the representation of a bank account inside a financial institution. A user can have one or more accounts in an institution. 

For example, one user (or link) can have a checking account, several credit cards, and a loan account.

Querying for a user's account information is useful as you can get information regarding:

- what types of accounts the user has
- the balance for each account (savings, checking, credit card, loan, and so on)


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