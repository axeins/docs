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
