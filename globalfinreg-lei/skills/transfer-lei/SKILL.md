---
name: transfer-lei
description: Use when the user wants to move or transfer an existing LEI (Legal Entity Identifier) to Global FinReg from another provider or LOU.
---

# Transfer an LEI to Global FinReg

1. Call `get_lei_record` to confirm the LEI, the entity and its current managing LOU.
2. Call `get_current_user` to confirm the user is signed in. If they have no account, call `create_user`.
3. **POA.** Ask how they want to handle the transfer power of attorney: sign online, have it emailed, or download it and sign by hand.
4. If the LEI expires within 2 months, tell the user it must be renewed with the transfer.
5. Call `start_lei_transfer`.
6. If the POA is signed by hand, give the user the `uploadUrl` from the response (or call `get_upload_link`) to upload the signed file in their browser. **Never pass a PDF as base64.**
7. Follow progress with `check_transfer_status` and tell the user when the transfer is complete.
