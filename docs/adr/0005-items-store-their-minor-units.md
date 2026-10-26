# A bill or an income stores its currency's minor units

mess stores money as an integer count of minor units, and a code's minor units come from the ISO 4217 data in a library. When the user adds a bill or an income, mess validates the currency code and looks up its minor units one time, then stores the count with the item. After that, mess reads every amount of the item with the stored count and never looks it up again. We chose this over a lookup at each read because a library upgrade can withdraw a code (BGN in 2026) or change its minor units, and then the stored integers of an old item would fail to load or change their meaning.

## Considered Options

- **Look up the minor units at each read.** Rejected: an upgrade can make an old item unreadable or change its amounts.
- **Use the library's money type (`bojanz/currency` `Amount`) in the domain.** Rejected: it always takes the minor units from the library's registry, so it cannot load an item with a withdrawn code, and it would be a second decimal type next to shopspring/decimal.

## Consequences

- Only add validates a currency code. Do not "fix" a load to validate the code again: a withdrawn code on a stored item is valid data.
- The minor units lock with the currency after the item's first row.
- The domain's money type takes its minor units from the item, not from the library.
