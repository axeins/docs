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
  "id": "8c3460e9-6126-4ae9-8dc6-7aa18b9e3742",
  "client": 12345,
  "year": 2024,
  "type": "debit",
  "reason": null,
  "account": 16000000,
  "contraAccount": 12100000,
  "recordDate": "2025-01-02",
  "deliveryDate": null,
  "date": "2025-01-02",
  "isGeneralReversal": false,
  "isOpeningBalance": false,
  "amount": 194.28,
  "currency": "EUR",
  "description": "RETOOL",
  "costCenter1": "302",
  "costCenter2": null,
  "invoiceNr": "C802CAFE-0078",
  "receiptNr": null,
  "batch": "01-2024/0004",
  "correlations": []
}
```

You can access your accounting entries by performing a `GET` request against the following endpoint:

```
https://app.ax1.ai/api/alpha/accounts/<account>/accounting/<year>/entries
```

The request will return an array of entries, e.g.:

```json
[
  {
    "id": "8c3460e9-6126-4ae9-8dc6-7aa18b9e3742",
    "client": 12345,
    "year": 2024,
    "type": "debit",
    // ...
  },
  {
  {
    "id": "d2a1134a-99ce-4d62-9b40-b66c829a162b",
    "client": 12345,
    "year": 2024,
    "type": "credit",
    // ...
  },
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
