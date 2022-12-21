# API reference introduction

Welcome to Belvo's API Reference documentation! We're always hard at work to improve the experience for our developers - because we all know you want to get things working as quickly and smoothly as possible.

# 📖 OpenAPI specification file

If you would like to download our API reference specification file, just click on the format you prefer: 

- <a href="https://statics.belvo.io/openapi-specs/BelvoOpenFinanceApiSpec.json" target="_blank">JSON format</a> (opens in separate browser tab)
- <a href="https://statics.belvo.io/openapi-specs/BelvoOpenFinanceApiSpec.yaml" target="_blank">YAML format</a> (automatically prompts to download the file)

# ℹ️ OpenAPI: required and nullable fields

In our API specification, you'll see that some response parameters will have a **required** annotation. According to the OpenAPI specification, when a response parameter is marked as **required**, this means that the response key _must_ be returned. However, the value of that response parameter can be `null`.


<div style="background-color:#f4f6f8; border-left: 6px solid #5bc0de;padding: 12px;margin-left: 25px; border-radius: 4px; margin-right: 25px"> In short, any response parameter marked as **required** will be returned by our API, but the value can be set to `null`. </div>

If you'd like to have more in-depth information about which field can be required and `null`, check out our [OpenAPI specification file](https://developers.belvo.com/reference/using-the-api-reference#-openapi-specification-file).

# 📞 Make API requests straight from the documentation

Just add your secret keys, select the right environment, and fill in the details for your call! All the required fields are automatically highlighted for you in <b style="color:red">red</b> and there's automatic data validation so you'll always know exactly what parameters you need to provide.


<div style="background-color:#f4f6f8; border-left: 6px solid #d9534f;padding: 12px;margin-left: 25px; border-radius: 4px; margin-right: 25px"> Your API keys will be stored for a given page for the duration of your browser session. We highly recommend you only use your Sandbox credentials while using the interactive API. </div>

<div style="display: flex; flex-direction: column; align-items: center;">
  <img src="https://files.readme.io/834b04f-api-ref-try-it-now.gif" alt="api-ref-try-it-now.gif">
  <span style="font-style: italic;">Making a request straight from the documentation</span>
</div>


<div style="background-color:#f4f6f8; border-left: 6px solid #50af51;padding: 12px;margin-left: 25px; border-radius: 4px; margin-right: 25px"> Auto-filled cURL requests

When you test our API using cURL, our API reference will automatically construct the right payload for you! </div>

# 🔍 See Belvo SDK examples

For all our API calls, you can see examples of our SDKs. Just click on the **Node**, **Python**, or **Ruby** icon, and see an example call!


<div style="display: flex; flex-direction: column; align-items: center;">
  <img src="https://files.readme.io/d59a21e-api-ref-sdks.gif" alt="api-ref-sdks.gif">
  <span style="font-style: italic;">Viewing Belvo SDK examples</span>
</div>

Additionally, you can also see auto-generated code examples for the most popular languages.

# 📃 View the response schema and examples

To view the response schema, just click on the response type in the **Responses** section of the call. What's more - we've included plenty of sample responses for most endpoints!


<div style="display: flex; flex-direction: column; align-items: center;">
  <img src="https://files.readme.io/553c5bf-api-ref-responses-examples.gif" alt="api-ref-responses-examples.gif">
  <span style="font-style: italic;">Viewing response documentation and examples</span>
</div>

## 🔦 Response filtering examples

In addition to our general [guide about Filtering responses](https://developers.belvo.com/docs/searching-and-filtering), for all our LIST requests we've included examples on how to apply filtering in cURL, Node, Python, and Ruby. 

![](https://files.readme.io/64a896f-api-ref-filtering-examples.gif "api-ref-filtering-examples.gif")

# 🐞 Report documentation bugs

Did you see something that wasn't quite right? Or have a suggestion? Just use the Feedback widget at the bottom of any page or email us at `docs@belvo.com` :smiley:!

# 📬 Postman - We still have it!

Of course, we know you love Postman - so don't worry. We'll always keep our Postman Public Workspace up to date with all the new developments we make to our API.

To get set up, just follow our dedicated guide on [Setting up our Postman collection](https://developers.belvo.com/docs/test-with-postman).

# 🥺 Errors?

We all hate getting errors - that's why we've created a pretty exhaustive list on how to troubleshoot them in our [API and Widget Errors](https://developers.belvo.com/docs/belvo-api-errors) documentation.