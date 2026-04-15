# customersuccess-mutual-success-plan
Mutual Success Plan for CSM
Now I have everything I need. Here's the README for the Mutual Success Plan skill:

Mutual Success Plan (MSP) Skill — README
What It Does
This skill helps Customer Success Managers (CSMs) and Account Executives (AEs) build a complete Mutual Success Plan — the "North Star" document that anchors a customer partnership around business outcomes rather than product features.
It handles the full MSP workflow: ingesting Salesforce data to auto-fill known fields, guiding the user through the remaining inputs conversationally, and producing a polished, structured MSP — either inline in chat or as a downloadable Word document.

When It Triggers
The skill activates when a user mentions any of the following (or similar):

"MSP", "Mutual Success Plan", "success plan", "account plan", "customer success plan"
"Help me build a plan for [customer]"
"I need to document our goals with [customer]"
"Prep a success plan for my renewal"
Salesforce data is pasted or referenced alongside a customer relationship task


How It Works
Step 1 — Salesforce Auto-Population
When Salesforce data is provided (pasted text, CSV export, or described fields), the skill automatically maps these 12 fields — and never asks the user for them manually:
FieldSalesforce SourceAccount NameAccount.NameCustomer WebsiteAccount.WebsiteIndustryAccount.IndustryARROpportunity.Amount or Account.ARR__cLaunch DateContract.StartDateRenewal DateContract.EndDateSKU / ProductOpportunity.ProductAE NameOpportunity.OwnerCSM NameAccount.CSM__cTechnical/Solutions ConsultantOpportunity.Solutions_Consultant__cExecutive SponsorContact (Role = Executive Sponsor)Economic BuyerContact (Role = Economic Buyer)
It confirms what was pulled ("✅ Pulled from Salesforce: ...") and flags gaps ("⚠️ Could not find: ...").
Step 2 — Manual Field Collection
The skill then guides the CSM/AE through the remaining fields in three conversational groups:
Stakeholders — Champion, Onboarding POC, Ongoing Support POC, Public/Private status
Strategy — Current State, Future State, 3 Business Goals, 3 Department Goals, KPIs (with a nudge toward specificity — e.g., "reduce time-to-hire by 30%", not "improve efficiency")
Operations — Client Commitments, Our Commitments, Communication Plan (meeting type, cadence, attendees)
Step 3 — MSP Generation
Once fields are collected, the skill produces a complete MSP with all sections: Company Overview, Internal Team, Client Stakeholders, Strategy & Vision, KPIs, and Execution & Operations.

Output Formats

Default: Clean, structured Markdown rendered inline in chat
On request: Exports a formatted .docx Word document (leverages the docx skill)


Built-in Quality Checks
Before delivering the MSP, the skill verifies:

All Salesforce fields are filled or marked [TBD]
KPIs are measurable, not vague
Business Goals and Department Goals are distinct from each other
Communication Plan includes at least one cadence item
Future State is outcome-oriented, not product-feature-oriented


Edge Cases
SituationBehaviorPartial Salesforce dataFills what's available; marks gaps [TBD]User says "just build it"Generates intelligent placeholders based on industry/product, marked [Draft — needs review]Edit/update requestRevises only the requested section; full re-render on requestNo Salesforce data at allProceeds with blanks; prompts user to fill auto-populate fields manually

Installation
Install the .skill file through your Claude skill manager. No additional dependencies required. The docx export feature requires the docx skill to also be installed.
