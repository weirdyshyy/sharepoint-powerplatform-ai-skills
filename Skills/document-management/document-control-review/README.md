# Document Control Review

A reusable Copilot in SharePoint skill for reviewing documents
against common document-control requirements.

## Purpose

The skill reviews selected SharePoint documents for:

- Missing required metadata
- Expired review dates
- Upcoming document reviews
- Document status
- Metadata quality
- Publishing readiness

## Results

Each document receives one of three results:

### Ready

Used when:

- All required metadata is complete
- Document Status is Approved or Published
- Review Date is valid
- No blocking issue exists

### Warning

Used when:

- No blocking issue exists
- Review Date falls within the next 30 days
- A minor nonblocking issue requires attention

### Action Required

Used when:

- Required metadata is missing
- Review Date has expired
- Document Status is Draft or Under Review
- Required information cannot be accessed
- Another blocking document-control issue exists

## Required Metadata

The example implementation evaluates:

- Document Type
- Department
- Document Status
- Document Owner
- Effective Date
- Review Date
- Review Period Months

These fields can be adapted to the metadata model of the
target SharePoint environment.

## Output

The skill returns:

| Document | Document-Control Result | Issue | Recommended Action |
|---|---|---|---|

It also returns summary counts for:

- Ready
- Warning
- Action Required

## Installation

Deploy the skill to:

Agent Assets/Skills/document-control-review/SKILL.md

on a SharePoint site where Copilot in SharePoint skills are available.

## Usage

Select the documents to review and ask Copilot:

Run document-control-review against these selected documents.

The skill can also be selected automatically for requests such as:

- Review these documents for document-control issues.
- Which documents have missing metadata?
- Are these documents ready for publishing?
- Check these documents for overdue reviews.

## Testing

Version 1.0 was tested against scenarios including:

| Scenario | Expected Result |
|---|---|
| Complete Approved document | Ready |
| Review due within 30 days | Warning |
| Missing required metadata | Action Required |
| Expired Review Date | Action Required |
| Draft document | Action Required |

## Version

**1.0**

Status: Validated

## Notes

This example is designed for demonstration and development purposes.

Required metadata and document-control rules should be adapted to
the governance requirements of the target organization.
