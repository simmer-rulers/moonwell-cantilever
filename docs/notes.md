# Moonwell Cantilever — Internal Notes

This document contains internal documentation for maintainers.

---

## Validation Steps

Before merging changes:

- [ ] Verify `chainId` values against official Base documentation
- [ ] Ensure RPC URLs are public, stable, and not hardcoded elsewhere
- [ ] Confirm explorer URLs match the correct network
- [ ] Check that the default network remains `base-mainnet`
- [ ] Validate JSON structure and formatting
- [ ] Ensure no secrets, API keys, or private endpoints are committed

---

## Dependency Rationale

Dependencies should align strictly with the Base / Coinbase ecosystem.

Guidelines:
- Prefer Base-native or Base-compatible SDKs
- Avoid overlapping libraries with similar responsibilities
- Keep dependency count minimal and justified
- Document why each dependency exists (wallet, RPC, UI, automation, etc.)

Network metadata **must not** be duplicated in code — always read from
`config/networks.json`.

---

## Maintenance Notes

- All network configuration lives in `config/networks.json`
- Adding a new Base network requires:
  1. Adding a new entry to the config file
  2. Verifying RPC and explorer stability
  3. Updating validation checklist if needed
- Mainnet is the production default
- Sepolia is intended for testing and development only

---

_Last updated: initial scaffold_
