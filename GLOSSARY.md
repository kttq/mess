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
