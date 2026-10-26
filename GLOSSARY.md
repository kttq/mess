# mess

mess is a local-first terminal app to plan a month: fixed bills, chores, income, spending buckets, and notes, with a history of each past month.

## Language

**Data directory**:
The one folder where mess keeps the user's data. The user can choose it; otherwise mess uses a default place for each operating system.
_Avoid_: data folder, store, home, config dir

**Open month**:
The one month that the user works on now. Only the open month's rows can change.
_Avoid_: current month, active month

**Closed month**:
A month that the user has closed. It is final: its rows never change, and it does not open again.
_Avoid_: past month, archived month

**Close**:
The user's act that makes the open month a closed month and opens the next month. Close carries nothing over to the next month.
_Avoid_: rollover, archive, end the month

**Expected amount**:
The amount that the user plans to pay for a bill, or to receive for an income, in one month. A new month expects the previous month's actual amount, or the previous month's expected amount if there is no actual amount. The user can change it while the row is not paid or not received.
_Avoid_: budget, planned amount, default amount

**Actual amount**:
The amount that the user really paid or received in one month. It is only a record: the paid or received mark, not the actual amount, tells if the row is done. When the user marks a row without an actual amount, the actual amount becomes the expected amount.
_Avoid_: real amount, paid amount

**Bill**:
A payment that the user plans to make each month, from its start month to its end month. A bill can have no end month. A card's statement is an ordinary bill.
_Avoid_: installment, expense, payment
