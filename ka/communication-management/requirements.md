# Requirements to confirm

## Confirmed scope

- The source team provides a CSV file. Power Automate loads the records into Dataverse.
- A Power Apps Canvas app presents the data and processing outcomes.
- Power Automate performs daily processing, assesses trigger and completion events, and applies eligibility rules.
- Blocks are stored in Dataverse and can be applied or removed according to the rules.
- Third-party services send communications through APIs.
- Updated data returns to the source through Power Automate. CSV is the proposed return format.

| Day | Communication | Decision still needed |
| --- | --- | --- |
| 1 | Service alert | Start date and eligibility |
| 30 | Email | Eligibility |
| 60 | Service alert | Eligibility |
| 90 | Email or letter | Channel selection and eligibility |
| 120 | Email or letter | Channel selection and eligibility |
| 150 | Closure letter, required | Treatment of earlier completion or cancellation |

## Questions for requirements gathering

| Area | Questions |
| --- | --- |
| Source CSV | Where is the file delivered? What are its columns, encoding, quoting rules, record identifier and delivery frequency? |
| Record updates | Is each CSV a full snapshot or a delta? How are duplicates, changed records, removed records and invalid rows handled? |
| Day counting | Which date starts Day 1? Are these calendar or business days? What happens when a milestone is missed or a record arrives late? |
| Schedule | What daily run time and time zone are required? When must intake and return files be processed? |
| Trigger events | What starts the business process? Which source fields or changes identify that event? |
| Eligibility | Which conditions permit each communication and block action? When must eligibility be checked again? |
| Completion events | What completes the business process? Does completion suppress later messages? How does that interact with the required Day 150 closure letter? |
| Block changes | Which blocks exist? When is each applied, retained or removed? Does the change depend on an API accepting a request or on confirmed delivery? |
| Channel selection | What selects email versus letter on Days 90 and 120? What happens when contact details are missing or a channel fails? |
| Delivery APIs | Which providers and endpoints are used for alerts, emails and letters? What authentication, templates, limits and status reporting do they support? |
| Status and retries | Does an API response mean accepted or delivered? How are final delivery, failures, retries and duplicate sends tracked? |
| Canvas app | Which views, filters and bulk controls are required? Can users edit data, request actions, override rules or reprocess failures? |
| Return file | Confirm CSV as the format. Which records and columns are returned, where, and how does the source confirm receipt and reconcile updates? |
| Scale and access | How many records and communications are expected daily? Who can view or change data? What history and retention are required? |

The workflow shows a proposed order: intake, assess each record, update blocks, send due communications, record outcomes, and return results. Rule precedence, failure paths and dependencies must be agreed before this becomes an implementation design.
