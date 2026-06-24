# Risk Register

Last updated: 2026-06-24.

| ID | Risk | Impact | Current level | Mitigation | Trigger / evidence |
|---|---|---|---|---|---|
| R-001 | Business relationship with manufacturer is not formalized | Product may promise services, prices or responsibility that no party owns | Critical | Complete D-001; define contract, money flow, warranty and non-circumvention before Product Gate | Partner terms remain verbal |
| R-002 | Building a catalogue instead of transaction infrastructure | High traffic may not improve purchase completion or operations | High | Use MemorialCase as core; require every capability to reduce uncertainty or advance a case | Backlog dominated by pages and visual effects |
| R-003 | False pricing precision | Loss of trust, disputes and margin leakage | Critical | Create pricing confidence model; show assumptions, ranges and version date; human validation at required points | Exact price shown without site/material/logistics data |
| R-004 | Scope expands into full ERP too early | Slow delivery and unusable first release | High | Release by narrow vertical journeys; defer inventory/accounting depth until validated | Large horizontal data-model tasks without user flow |
| R-005 | Approval errors in names, dates, portrait or design | Irreversible financial and emotional harm | Critical | Immutable versions, separate approvals, audit log, production gate | Production can start without explicit proof approval |
| R-006 | Personal and memorial data leakage | Legal, ethical and reputational damage | Critical | Data minimization, role-based access, private media, audit, retention rules and Russian hosting/legal review | Public URLs or analytics receive personal content |
| R-007 | Real workflow differs from software assumptions | Team bypasses the system; duplicate chats and files return | High | Service blueprint with sales, designer, production and installer; field validation before automation | Users copy data into messengers/spreadsheets |
| R-008 | Partner dependency and capacity failure | Delays, inability to honour promises | High | Record capacity and seasonal rules; SLA/confirmation stage; alternative-path planning later | Manufacturer does not confirm order/lead time digitally |
| R-009 | Lack of real media and proof | Site appears generic or untrustworthy | Medium | Build media shot list and evidence provenance; use honest placeholders before launch | Stock/generated images presented as real work |
| R-010 | Emotionally insensitive conversion tactics | Reputational damage and low-quality leads | High | Ban pressure timers, fake scarcity and guilt; review copy and flows against empathy principles | Discount pressure dominates the user journey |
| R-011 | 3D/configurator overengineering | Costly feature does not improve decisions | Medium | Start with guided brief, composable 2D/real examples and proof workflow; validate need for 3D | 3D becomes prerequisite for Release 1 |
| R-012 | Codex silently expands scope or reports incomplete work | Architectural drift and false completion | High | One Issue/branch/PR; acceptance criteria; evidence template; manager review before merge | PR lacks issue, tests, docs or screenshots |
| R-013 | Direct commits to main bypass review | Loss of project control | High | Configure branch protection; require PR and checks; owner-only emergency bypass | Non-governance implementation commit appears on main |
| R-014 | Metrics optimize leads rather than completed, healthy orders | More unqualified enquiries and operational overload | Medium | Track structured-case quality, proposal time, approval errors, conversion, fulfilment and claims | Success reported only as traffic/form submissions |

## Review rule

Every Product Gate review and material implementation PR must check whether it changes the likelihood or impact of any risk. New risks are appended; existing history is not deleted.
