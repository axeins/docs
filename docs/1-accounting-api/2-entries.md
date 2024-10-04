---
---

# Entries

Accounting entries are the most fundamental block of an accounting system. Your _books_
are essentially a list of accounting entries.

In accounting terms, an accounting entry, transfers _money_ from one account to another.
A buiness transaction (e.g. revenue or salary payment) is _accounted for_ by creating
a number of accounting entries that model the business transaction in accounting terms.

The schema of an entry is as follows:

```json
{
  "creditAccount": 12345,
  "debitAccount": 54321,
  "recordDate": "2024-04-12",
  "deliveryDate": null,
  "date": "2024-04-12",
  "amount": 132.30,
  "isOpeningBalance": false,
  "isGeneralReversal": false,
  "description": "Trackpad purchase",
  "costCenter": "303"
};
```

You can access your accounting entries by performing a `GET` request against the following endpoint:

```
https://app.ax1.ai/api/alpha/accounts/<account>/accounting/<year>/entries
```

The request will return an array of entries, e.g.:

```json
[
  {
    "creditAccount": 12345,
    "debitAccount": 54321,
    "recordDate": "2024-04-12",
    "deliveryDate": null,
    "date": "2024-04-12",
    "amount": 132.3,
    "isOpeningBalance": false,
    "isGeneralReversal": false,
    "description": "Trackpad purchase",
    "costCenter": "303"
  },
  {
    // ...
  }
]
```

Here is a full example of a request using `curl`:

```bash
curl \
    --header "Authorization: Bearer <my-access-token>" \
     http://app.ax1.ai/api/alpha/accounts/12345/accounting/2023/entries
```
