---
---

# Accounts

Access accounts referred to in accounting entries. Accounts are one of three
types:

- General ledger accounts: expenses, revenues, etc.
- Creditor accounts: your suppliers
- Debitor accounts: your clients

Accounts are scoped by financial year and may change year-over-year. You must only join
accounts of a specific year on accounting entries of that same year. Only then are you
sure to be able to match all entries to an account.

The schema of an account is as follows:

```json
{
  "number": 1234567,
  "description": "A humanly-readable description of the account",
  "type": "general|debitor|creditor"
}
```

You can access your accounts by performing a `GET` request against the following endpoint:

```
https://app.ax1.ai/api/alpha/accounts/<account>/accounting/<year>/accounts
```

Parameters:

- `account` your account ID (e.g. `12345`)
- `year` the financial year (e.g. `2024`)

The request will return an array of accounts, e.g.:

```json
[
  {
    "number": 123456,
    "description": "Apple Inc.",
    "type": "creditor"
  },
  {
    "number": 112233,
    "description": "Best Customer Ltd.",
    "type": "debitor"
  },
  {
    "number": 100001,
    "description": "Revenue (19%)",
    "type": "general"
  }
]
```

Here is a full example of a request using `curl`:

```bash
curl \
    --header "Authorization: Bearer <my-access-token>" \
     http://app.ax1.ai/api/alpha/accounts/12345/accounting/2023/accounts
```
