# A row holds only month data, so a rename shows in history

A bill, chore, or income holds its identity: name, currency, due day, start month, and end month. A row holds only what is true for one month: its expected and actual amounts, its mark, and for a paid bill, cash or card. We chose this over rows that copy the name and the due day, because a bill is one thing that the user pays each month, and one source for each fact needs no copies to keep in sync.

## Consequences

- A rename or a due-day edit shows in every month, also in closed months. "A closed month never changes" means that its month data never changes. Do not add name or due-day columns to rows to "fix" history.
- A closed row does not keep the due day that applied in its month. If a later map must show "paid late" in history, it needs a new stored value.
- Currency, start month, and start amount can change only while the item has no row, because rows depend on them.
