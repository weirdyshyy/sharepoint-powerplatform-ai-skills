---
name: document-control-review
description: |-
  Review selected SharePoint documents for document-control issues, missing metadata, overdue reviews, and publishing readiness.

  Use when the user says:
  - "review documents"
  - "perform a document-control check"
  - "identify missing metadata"
  - "identify overdue document reviews"
  - "check publishing readiness"
  - "review document metadata quality"
---
## When to use
Use this skill to review one or more selected SharePoint documents for document-control completeness, review-date risks, metadata quality, consistency, and publishing readiness.

This skill is read-only. Do not modify documents, metadata, file names, locations, or publication status unless the user explicitly requests a separate modification action.

## Inputs
- One or more selected SharePoint documents.
- Available SharePoint metadata for each document.
- The current date for review-date evaluation.

## Required metadata
For every reviewed document, check these required metadata fields:
- Document Type
- Department
- Document Status
- Document Owner
- Effective Date
- Review Date
- Review Period Months

## Information states
Use these terms precisely:
- **Missing metadata:** The SharePoint field exists but contains no value.
- **Information not found:** The information isn't present in the available source.
- **Information couldn't be accessed:** The information exists or may exist, but it couldn't be retrieved or read.

For required metadata:
- A blank field value is **Action Required**.
- A required value that couldn't be accessed is **Action Required**, because publishing readiness can't be verified.
- Do not invent metadata or infer unavailable values.

## Steps
1. Identify the selected documents and retrieve available metadata and document-control information.
2. Check every required metadata field.
3. Evaluate document status, review-date validity, consistency, and publishing readiness.
4. Record specific issues using the information-state terms above where applicable.
5. Assign one result per document using the decision structure below.
6. Keep the review read-only. Do not modify documents, metadata, file names, locations, or publication status.

## Decision structure
Apply the highest-severity result that matches:

### Action Required
Assign **Action Required** when any of these apply:
- Any required metadata field is blank.
- Required metadata or information can't be accessed, so publishing readiness can't be verified.
- Review Date is earlier than the current date.
- Document Status is Draft or Under Review when evaluating publishing readiness.
- Another blocking document-control issue exists.

### Warning
Assign **Warning** only when no Action Required condition exists and one or more of these apply:
- Review Date falls within the next 30 days, including today through 30 days from today.
- Nonrequired information couldn't be verified.
- A minor inconsistency exists that doesn't prevent normal use.

### Ready
Assign **Ready** only when all of these apply:
- All required metadata is populated and accessible.
- Document Status is Approved or Published.
- Review Date is today or in the future.
- No significant document-control issue exists.
- No Warning condition applies.

## Date rules
- A Review Date is expired only when it is earlier than the current date.
- A Review Date equal to today isn't expired.
- A future Review Date must never be described as overdue.
- If Review Date is within the next 30 days, assign Warning unless an Action Required condition exists.

## Output format
Return exactly these columns:

| Document | Document-Control Result | Issue | Recommended Action |
|---|---|---|---|

After the table, provide:
- Total documents reviewed
- Total Ready
- Total Warning
- Total Action Required
- Most common issues
- Recommended next actions

## Rules
- Keep findings specific to each document.
- State whether information is missing, not found, or couldn't be accessed.
- Don't duplicate classification rules across the response.
- Don't modify documents or SharePoint metadata.
- Don't delete, move, rename, publish, archive, or update documents unless the user explicitly requests a separate modification action.
- Ask for clarification only when it's required to safely complete a requested modification.


name: document-control-review description: |- Review selected SharePoint documents for document-control issues, missing metadata, overdue reviews, and publishing readiness.

Use when the user says:

"review documents"
"perform a document-control check"
"identify missing metadata"
"identify overdue document reviews"
"check publishing readiness"
"review document metadata quality"
When to use
Use this skill to review one or more selected SharePoint documents for document-control completeness, review-date risks, metadata quality, consistency, and publishing readiness.

This skill is read-only. Do not modify documents, metadata, file names, locations, or publication status unless the user explicitly requests a separate modification action.

Inputs
One or more selected SharePoint documents.
Available SharePoint metadata for each document.
The current date for review-date evaluation.
Required metadata
For every reviewed document, check these required metadata fields:

Document Type
Department
Document Status
Document Owner
Effective Date
Review Date
Review Period Months
Information states
Use these terms precisely:

Missing metadata: The SharePoint field exists but contains no value.
Information not found: The information isn't present in the available source.
Information couldn't be accessed: The information exists or may exist, but it couldn't be retrieved or read.
For required metadata:

A blank field value is Action Required.
A required value that couldn't be accessed is Action Required, because publishing readiness can't be verified.
Do not invent metadata or infer unavailable values.
Steps
Identify the selected documents and retrieve available metadata and document-control information.
Check every required metadata field.
Evaluate document status, review-date validity, consistency, and publishing readiness.
Record specific issues using the information-state terms above where applicable.
Assign one result per document using the decision structure below.
Keep the review read-only. Do not modify documents, metadata, file names, locations, or publication status.
Decision structure
Apply the highest-severity result that matches:

Action Required
Assign Action Required when any of these apply:

Any required metadata field is blank.
Required metadata or information can't be accessed, so publishing readiness can't be verified.
Review Date is earlier than the current date.
Document Status is Draft or Under Review when evaluating publishing readiness.
Another blocking document-control issue exists.
Warning
Assign Warning only when no Action Required condition exists and one or more of these apply:

Review Date falls within the next 30 days, including today through 30 days from today.
Nonrequired information couldn't be verified.
A minor inconsistency exists that doesn't prevent normal use.
Ready
Assign Ready only when all of these apply:

All required metadata is populated and accessible.
Document Status is Approved or Published.
Review Date is today or in the future.
No significant document-control issue exists.
No Warning condition applies.
Date rules
A Review Date is expired only when it is earlier than the current date.
A Review Date equal to today isn't expired.
A future Review Date must never be described as overdue.
If Review Date is within the next 30 days, assign Warning unless an Action Required condition exists.
Output format
Return exactly these columns:

Document	Document-Control Result	Issue	Recommended Action
After the table, provide:

Total documents reviewed
Total Ready
Total Warning
Total Action Required
Most common issues
Recommended next actions
Rules
Keep findings specific to each document.
State whether information is missing, not found, or couldn't be accessed.
Don't duplicate classification rules across the response.
Don't modify documents or SharePoint metadata.
Don't delete, move, rename, publish, archive, or update documents unless the user explicitly requests a separate modification action.
Ask for clarification only when it's required to safely complete a requested modification.
