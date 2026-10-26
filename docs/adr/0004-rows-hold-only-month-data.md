# A row holds only month data, so a rename shows in history

A bill, chore, or income holds its identity and its defaults: name, currency, start month, end month, recurrence, and for a bill or a chore, an optional default due day. A row holds only what is true for one month: its due day, its expected and actual amounts, its mark, and for a paid bill, cash or card. A row copies the default due day when it is made, clamped to the last day of the row's month, and the user can change it while the month is open and the row is not marked. We chose this over rows that copy the name, because a bill is one thing that the user pays each month, and one source for each fact needs no copies to keep in sync. The due day is different: some due dates change each month (for example a card statement), so it is a fact about one month.

## Consequences

- A rename shows in every month, also in closed months. "A closed month never changes" means that its month data never changes. Do not add a name column to rows to "fix" history.
- A closed row keeps the due day that applied in its month, so a later history map can show "paid late" with no new stored value.
- Currency, start month, and start amount can change only while the item has no row, because rows depend on them.
