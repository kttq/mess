# A month closes only by hand, and a closed month is final

The user closes the open month by hand. Close is allowed only when today is in a later calendar month, and each close moves forward exactly one month, also when the user is behind the calendar. A closed month never opens again. We chose this over an automatic rollover on the first of the month so that the user can record a late payment (for example, rent paid on the 31st and entered on the 2nd) and review the month before it becomes final.

## Consequences

- Do not add an automatic rollover. The open month can stay behind the calendar until the user closes it.
- Do not add a reopen operation. History and the edit rule depend on final closed months.
- Close refuses an early call with a named error. The UI uses the close preview to gray out the action, so the date rule lives only in the backend.
