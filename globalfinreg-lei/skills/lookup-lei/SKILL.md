---
name: lookup-lei
description: Use when the user wants to find, check or verify a company's LEI (Legal Entity Identifier), look up an LEI record, check whether an LEI is active or lapsed, or see LEI prices.
---

# Look up an LEI

These tools need no sign-in.

1. To find a company's LEI, call `search_lei_by_company_name` with the company name. If several match, show the name, country, LEI and status of each, and ask which one is meant.
2. For full details on a known LEI, call `get_lei_record`. Report the legal name, registered address, status, next renewal date and managing LOU.
3. If the LEI is lapsed or expires within 2 months, say so and offer to renew it (see the renew-lei skill). If it is managed by another provider, mention that it can be transferred to Global FinReg and renewed at the same time.
4. For pricing questions, call `get_prices`.
5. If the company has no LEI, offer to register one (see the register-lei skill).
