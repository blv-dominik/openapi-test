Belvo's Risk Insights endpoint exposes a set of features that can be used to improve your company's credit risk and opportunity decisions. This set of features can be used as building blocks to create or iterate on your credit score using transactional banking data to improve the predictive power of your models. You can use these components as you require and make the most sense for your specific use case. 

We take up to 90 days of transactional data from the user's checking, savings, loans, and credit card accounts to calculate the risk insights.

If you need to know the currency of the account, do a GET Details to the Accounts endpoint (using the account ID you receive from in the accounts array of the response).

### **🔦 Filterable fields**

Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.

| Field  | Available Filters |
| ------ | ----------------- |
| `id`   | `=`, `in`         |
| `link` | `=`, `in`         |

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