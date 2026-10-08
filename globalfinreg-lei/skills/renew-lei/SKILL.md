---
name: renew-lei
description: Use when the user wants to renew, extend or reactivate an LEI (Legal Entity Identifier), or asks which of their LEIs are expiring or lapsed.
---

# Renew an LEI

1. Call `get_current_user` to confirm the user is signed in.
2. To find what needs renewing, call `list_leis_due_for_renewal` (or `list_my_leis` for everything). Show each LEI's entity name and renewal date.
3. **If the LEI is managed by another provider**, it must be transferred, not renewed here. Use the transfer-lei skill. An LEI expiring within 2 months must be renewed together with its transfer.
4. **Currency.** Ask which currency they want to be charged in, and call `set_currency` if needed.
5. Call `get_renewal_quote`. Show the price and any multi-year options. **Wait for the user to agree.**
6. Ask whether they want to pay by card or invoice, then call `create_renewal_order`:
   - `card` returns a payment link. Give it to the user. **Never ask for card details.**
   - `invoice` returns the invoice PDF.
7. Check `get_renewal_payment_status` and `get_renewal_order` to confirm the renewal is complete.
