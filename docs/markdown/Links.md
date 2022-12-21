A **Link** is a set of credentials associated to an end-user's access to an **institution**.

<div style="background-color:#f4f6f8; border-left: 6px solid #808080;padding: 12px;margin-left: 25px; border-radius: 4px; margin-right: 25px">
<strong>Example: </strong> The username and password combination used to log in to an online banking application would be a link.
</div>

You will need to register a **Link** before accessing information from that specific end-user, such as account or transaction details.

<div style="background-color:#f4f6f8; border-left: 6px solid #4CAF50;padding: 12px;margin-left: 25px; border-radius: 4px; margin-right: 25px">
<strong>Note: </strong> We recommend using our <a href="https://developers.belvo.com/docs/connect-widget" target="_blank">Connect Widget</a> to handle link creation and link status updates.
</div>

You have the possibility to register two types of links:

### Recurrent links (default)

With recurrent links, Belvo automatically refreshes information weekly and notifies you via [Webhooks](https://developers.belvo.com/docs/webhooks) so you always have up-to-date data. Then, when you receive the webhook, you can make GET requests to the List or Detail endpoints to instantly access up-to-date information, without needing to connect to the institution.

<img src="https://files.readme.io/7b6c0d4-Recurrent_Link_FLow.png" alt="fiscal-endpoints" width="950">

You can also make POST calls directly to the institution, as with single links, as soon as the link is created. However, we recommend you follow the flow described above (waiting for the webhook event) for a more optimal experience.

### Single links

Single links are used to perform ad hoc data access to accounts, owners, transactions, and so on. For example, you can use it when you want to do an underwriting process to assess risk before lending money.

For single links, you have to perform POST calls to an institution **every time** you want to access fresh data.

<img src="https://files.readme.io/eda7956-Single_Link_Flow.svg" alt="fiscal-endpoints" width="950">