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

# Filtering results from two institutions and a certain status
https://sandbox.belvo.com/api/links/?institution__in=erebor_mx_retail,gringotts_mx_retail&status=invalid
```
```javascript Node
//  Filtering results to have links just from two institutions
client.links.list({
  filters: {
    institution__in: "erebor_mx_retail,gringotts_mx_retail"
  }
})

//  Filtering results from two institutions and a certain status

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

# Filtering results from two institutions and a certain status
client.Links.list(institution__in="erebor_mx_retail,gringotts_mx_retail", status="invalid")
```
```ruby Ruby
# Filtering results to have links just from two institutions:
client.links.list(params: {
  institution__in: "erebor_mx_retail,gringotts_mx_retail"
})

# Filtering results from two institutions and a certain status:
client.links.list(params: {
  institution__in: "erebor_mx_retail,gringotts_mx_retail",
  status: "invalid"
})
```