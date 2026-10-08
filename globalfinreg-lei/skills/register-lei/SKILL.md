---
name: register-lei
description: Use when the user wants to get, apply for, obtain or register a new LEI (Legal Entity Identifier) for a company, fund, trust or other legal entity.
---

# Register a new LEI

1. **Check for an existing LEI first** with `search_lei_by_company_name`. If one exists, offer renewal or transfer instead.
2. **Account.** Call `get_current_user`. If the user has no Global FinReg account, call `create_user`; they will get an email to set a password. Continue once they have signed in.
3. **Currency.** Ask which currency they want to be charged in. Call `set_currency` if it differs from the account's currency.
4. **Legal form.** If needed, call `lookup_legal_form` to find the right legal form code for the entity's jurisdiction.
5. **Limited POA.** Ask how they want to handle the limited power of attorney: sign online, have it emailed, or download it and sign by hand.
6. Call `start_lei_registration` with the entity details.
7. **Documents.** If the response says `documentsNeeded`, or the limited POA is signed by hand, give the user the `uploadUrl` from the response (or call `get_upload_link`) so they can upload the files in their browser. **Never pass a PDF as base64.**
8. **Quote.** Call `get_registration_quote` and show the price clearly. **Wait for the user to agree** before going on.
9. **Order.** Ask whether they want to pay by card or invoice, then call `create_registration_order`:
   - `card` returns a payment link. Give it to the user. **Never ask for card details.**
   - `invoice` returns an invoice PDF.
10. Follow progress with `check_registration_status` and tell the user when the LEI is issued.
