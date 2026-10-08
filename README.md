# Global FinReg LEI plugin for Claude

Look up, register, renew and transfer LEIs (Legal Entity Identifiers) with Global FinReg, directly from Claude.

## Install (Claude Code)

    /plugin marketplace add gfrdavid/globalfinreg-claude-plugin
    /plugin install globalfinreg-lei@globalfinreg

The first time you use the plugin, you'll be asked to sign in to your Global FinReg account (or create one). After that, all tools work without signing in again.

## What it does

- **Lookup**: find any company's LEI and check its status in the global LEI register
- **Register**: apply for a new LEI, upload documents and pay by card link or invoice
- **Renew**: see expiring LEIs and renew them
- **Transfer**: move an LEI from another provider to Global FinReg

Claude never asks for card details. Payments go through a secure Global FinReg payment link.
