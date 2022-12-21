# Deleting links in batches

To delete links in bulk, we recommend looping through the list of links you want to delete and making the delete request.

> 🚧 **Rate limiting and IP blocking**
> 
> An important technical note for performing operations in batches is to take into consideration our rate-limiting: up to 80 requests every 30 seconds. If you exceed this limit, you run the risk of Belvo blocking your IP from making further requests.
> 
> For more information, or if your IP address has been blocked, please contact our [support team](https://support.belvo.com/hc/en-us/requests/new).