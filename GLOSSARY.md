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

**Row**:
The record of one bill, chore, or income in one month: only what is true for that month, such as its due day, its amounts, and its mark. The name belongs to the bill, chore, or income, not to the row.
_Avoid_: entry, instance, month item

**Expected amount**:
The amount that the user plans to pay for a bill in one month. A new month expects the previous month's actual amount, or the previous month's expected amount if there is no actual amount. The user can change it while the row is not paid.
_Avoid_: budget, planned amount, default amount

**Actual amount**:
The amount that the user really paid for a bill in one month. It is only a record: the paid mark, not the actual amount, tells if the row is done. When the user marks a row without an actual amount, the actual amount becomes the expected amount.
_Avoid_: real amount, paid amount

**Bill**:
A payment that the user plans to make each month, from its start month to its end month. A bill can have no end month. A card's statement is an ordinary bill.
_Avoid_: installment, expense, payment

**Income**:
Money that the user plans to have in a month, from its start month to its end month. Each of its rows has one amount, which a new month copies from the previous row, and no mark, because it tells the user how much money they have to work with, not a task to do. A one-off income has the same start month and end month.
_Avoid_: salary, earning, received income

**Available**:
The money of one currency that is free in a month after its bills: the income amounts, minus each bill that is unpaid or paid with cash. A bill paid with a card does not count, because its money goes out with the card's statement bill.
_Avoid_: balance, money left, free money

**Pending**:
The money of one currency that the unpaid bills of a month still need: the sum of their expected amounts.
_Avoid_: still to pay, outstanding, due

**Overdue**:
A row of the open month that is not marked (not paid or not done), and whose due date is before today. A row with no due day is never overdue, and an income is never overdue.
_Avoid_: late, past due

**Recurrence**:
The months of the year in which a bill, chore, or income shows, for example only June and December. It has at least one month, and the default is all twelve.
_Avoid_: months of the year, mask, schedule
