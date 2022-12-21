A **balance** represents the amount of funds available in a checking or savings account over a period of time.

<ul>
  <li>
    If your Balance request is not for a checking or savings account, we return
    an empty array.
  </li>
  <li>
    If we cannot calculate the balance for a given day within your requested
    period, the <code>balance</code> and <code>current_balance</code> fields
    will return <code>null</code> for that day.
  </li>
</ul>

> 📘 
> 
> Savings accounts that do not have any associated transactions (for example, some _poupança_ accounts in Brazil) will not contain accurate Balance information. We do not recommend using the Balance endpoint for these types of accounts. 
> 
> Savings accounts vary from institution to institution, so we recommend that you first use our [Retrieve transactions for a link](https://developers.belvo.com/reference/retrievetransactions) request, adding the `account` in the request body, to see if the Savings account has any associated transactions.


### **🔦 Filterable fields**

Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.

| Field             | Available Filters                      |
| ----------------- | -------------------------------------- |
| `account`         | `=`, `in`                              |
| `account_type`    | `=`, `in`                              |
| `balance`         | `=`, `gt`, `gte`, `lt`, `lte`, `range` |
| `currency`        | `=`, `in`                              |
| `current_balance` | `=`, `gt`, `gte`, `lt`, `lte`, `range` |
| `id`              | `=`, `in`                              |
| `institution`     | `=`, `in`                              |
| `link`            | `=`, `in`                              |
| `value_date`      | `=`, `gt`, `gte`, `lt`, `lte`, `range` |

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