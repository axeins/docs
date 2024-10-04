# Authentication

API requests are authenticated using an `Authorization` request header in the format `Authorization: Bearer <access-token>`.

Here is an example of how you would authenticate a `GET` request using curl:

```bash
curl \
    --header "Authorization: Bearer <my-access-token>" \
     http://app.ax1.ai/api/alpha/accounts/12345/accounting/2023/entries
```
