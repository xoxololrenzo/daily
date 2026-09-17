[README_1.md](https://github.com/user-attachments/files/32327257/README_1.md)
# Daily

A single-file budgeting web app. It answers one question: **how much can I spend today?**

Not an expense tracker. A tracker tells you what you already spent. This works out what is
safe to spend, by taking your pay, holding back what is already committed, and dividing what
is left over the days remaining in the cutoff.

## How the daily number works

```
money on hand
  − set aside from past cutoffs
  − loans and bills due this cutoff
  − fare for the office days left
  − savings not yet funded
  ± manual adjustment
  = free to spend, divided by the days left
```

Anything already committed is held back **before** the division, so a loan payment never
looks like you blew the budget on lunch.

## What it does

- **Today** – one number, what is safe to spend, plus an affordability check
- **Envelopes** – balances by account, grouped into envelopes, with spending per envelope
- **Calendar** – every day of the cutoff against your pace, and week by week, Monday to Sunday
- **Loans** – the full payment schedule, by month, by lender, or upcoming, with card bills
  named for the month you spent and dated for when they are due
- **Plan a cutoff** – a sandbox for any future cutoff: change the pay, move a payment, trim
  the daily figure, and see whether it covers itself before it arrives

## Setup

No build step, no dependencies, no server. Open `index.html`.

To use it as a phone app: open the published page in Safari, Share, **Add to Home Screen**.
Installed that way, iOS keeps the data instead of clearing it after a week of not opening it.

## Your data

Everything lives in `localStorage` in one browser, on one device. Nothing is uploaded and
there is no account.

That has two consequences:

- **Export a backup regularly.** Setup → Your data → Export backup. Clearing site data,
  losing the phone, or reinstalling wipes everything.
- **Never commit a backup or a seed file to this repo.** It is public and those files contain
  real balances. `.gitignore` covers the usual names, but check before you commit.

Do not put card numbers, PINs, passwords or account logins in the app. It has no use for them.

## Updating

Replace `index.html`. The version shows in Setup, and Setup → Your data → **Check for app
update** forces the Home Screen copy past its cache.

Imports are backward compatible, so an older backup restores into a newer version.
