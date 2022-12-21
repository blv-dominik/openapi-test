At the moment we only support the following institutions and investment products:

| Institution                     | Portfolio                         | Instruments                 |
| ------------------------------- | --------------------------------- | --------------------------- |
| Banco de Brazil Retail (Brazil) | `FIXED_INCOME`                    | `DEPOSIT`                   |
| Banco Inter Retail (Brazil)     | `FIXED_INCOME`                    | `DEPOSIT`                   |
| Bradesco Retail (Brazil)        | `FIXED_INCOME`, `VARIABLE_INCOME` | `DEPOSIT`, `FUND`           |
| CaixaBank Retail (Brazil)       | `FIXED_INCOME`, `VARIABLE_INCOME` | `DEPOSIT`, `FUND`           |
| Itau Retail (Brazil)            | `FIXED_INCOME`, `VARIABLE_INCOME` | `DEPOSIT`, `FUND`, `STOCKS` |
| Santander Retail (Brazil)       | `FIXED_INCOME`, `VARIABLE_INCOME` | `DEPOSIT`, `BOND`, `FUND`   |


### **🔦 Filterable fields**

Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.

| Field         | Available Filters                 |
| ------------- | --------------------------------- |
| `created_at ` | `gt`, `gte`, `lt`, `lte`, `range` |
| `link`        | `=`, `in`                         |

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