# Global FinReg LEI plugin for Claude

Look up, register, renew and transfer LEIs (Legal Entity Identifiers) with Global FinReg, directly from Claude.

## Install (Claude Code)

    /plugin marketplace add gfrdavid/globalfinreg-claude-plugin
    /plugin install globalfinreg-lei@globalfinreg

You'll be asked to sign in to your Global FinReg account the first time an account action is needed.

## What it does

- **Lookup**: find a company's LEI and check its status (no sign-in needed)
- **Register**: apply for a new LEI, upload documents and pay by card link or invoice
- **Renew**: see expiring LEIs and renew them
- **Transfer**: move an LEI from another provider to Global FinReg

Claude never asks for card details. Payments go through a secure Global FinReg payment link.
