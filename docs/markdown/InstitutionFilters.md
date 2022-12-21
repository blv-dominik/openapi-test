### **🔦 Filterable fields**

Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.

| Field          | Available Filters |
| -------------- | ----------------- |
| `code`         | `=`, `in`         |
| `country_code` | `=`, `in`         |
| `display_name` | `=`               |
| `name`         | `=`, `in`         |
| `resources`    | `allin`           |
| `status`       | `=`, `in`         |
| `type`         | `=`, `in`         |
| `website`      | `=`               |

> 📘 Support for partial display_name searches
> 
> When filtering by `display_name`, our API supports partial searches of at least one character in length. For example, if you use `display_name=Banco`, we'll return Banco Bradesco, Banco do Brasil, Bancolombia, Banco de Bogotá, Banco Falabella, Hey Banco, and so on.

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