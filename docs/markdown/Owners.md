An **owner** represents the person who has access to a Link and is the owner of all the accounts inside the Link.

You can use this endpoint in order to get useful information about your client, such as:

- their full name
- key contact information
- information about the ID document they used when opening the account

### **🔦 Filterable fields**

Please see the table below for an alphabetized list of fields that you can filter your responses by. For more information on how to use filters, see our [Filtering responses](https://developers.belvo.com/docs/searching-and-filtering) article.

| Field         | Available Filters                 |
| ------------- | --------------------------------- |
| `created_at ` | `gt`, `gte`, `lt`, `lte`, `range` |
| `email`       | `=`                               |
| `id`          | `=`, `in`                         |
| `link`        | `=`, `in`                         |

```curl cURL
# Filtering results so that you get the emails of one link:
https://sandbox.belvo.com/api/owners/?email=filtering@belvo.com

```
```javascript Node
// Filtering results so that you get the emails of one link:
client.owners.list({
  filters: {
    email: "filtering@belvo.com"
  }
})

```
```python Python
# Filtering results so that you get the emails of one link:
client.Owners.list(email="filtering@belvo.com")

```
```ruby Ruby
# Filtering results so that you get the emails of one link:
client.owners.list(params: {
  email: "filtering@belvo.com"
})

})
```