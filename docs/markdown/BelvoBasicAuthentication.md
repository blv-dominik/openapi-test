Belvo employs **basic authentication** using your secret keys. Just use your secretId as the `username` and secretPassword as the `password`. For example:

```text Authentication example
curl \
    -u =BASE64-SECRET_ID=:=BASE64-SECRET_PASSWORD=
    https://sandbox.belvo.com/api/
```

For information on how to get your API keys, check out our [Get Started in 5 Minutes](https://developers.belvo.com/docs/get-started-in-5-minutes) DevPortal article.