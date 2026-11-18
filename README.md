# Capital Markets mock screens

Static pages used to demo UiPath RPA robots. Everything here is fictional: no real systems, clients or data, and no sign-in.

| Page | What a robot does |
|---|---|
| `crm.html` | Search a client by trade reference and read the client record |
| `cds.html` | Key in a settlement instruction and read the status by account |
| `gl.html` | Paste a trade's journal lines and post them |

Trade references the pages know: `TRD-CM-00001` to `TRD-CM-00012` (CDS and GL skip `00005`). Anything else shows a not-found or rejected message.

## Element ids (the contract with the robots)

Do not rename these without changing the robots.

- **crm.html**: `spnStatus` (always visible: "Client found." or "Rejected: ..."), `txtTradeId`, `btnSearch`, `divResultsPanel`, `divNotFound`, `spnTradeId`, `spnClientId`, `spnClientName`, `spnLei`, `spnRiskRating`, `spnRelationshipManager`, `spnCommissionSchedule`, `spnCommissionRate`, `spnOnboardingStatus`, `spnSsiOnFile`, `tblAccounts`, `tblStanding` (one line per row, fields separated by ` | `).
- **cds.html**: `spnStatus` ("Accepted by CDS." or "Rejected: ..."), `txtTradeId`, `txtSettleDate`, `txtAcct1..3`, `txtQty1..3`, `btnSubmit`, `divError`, `divConfirmation`, `spnTradeId`, `spnSettleDate`, `spnSubmittedAt`, `spnUpdatedAt`, `spnTradeStatus`, `tblResult`.
- **gl.html**: `spnStatus` ("Accepted: journal posted." or "Rejected: ..."), `txtTradeId`, `txtJournalLines` (one line per entry: entry id, date, account, debit, credit, amount, comma separated), `btnPost`, `divError`, `divConfirmation`, `spnPostingId`, `spnTradeId`, `spnLinesPosted`, `spnTotalDebits`, `tblPosted`.
