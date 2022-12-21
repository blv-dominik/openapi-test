Our **Tax status** endpoint lets you retrieve information about a person's or business's tax situation, according to the country's tax authority. 

- For SAT (Mexico), this information is extracted from the _Constancia de situación fiscal_ document.
- For DIAN (Colombia), this information is extracted from the _Registro Único Tributario_ document.



### **🔦 Filterable fields**

Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.

| Field         | Available Filters                 |
| ------------- | --------------------------------- |
| `created_at ` | `gt`, `gte`, `lt`, `lte`, `range` |
| `id`          | `=`, `in`                         |
| `link`        | `=`, `in`                         |

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