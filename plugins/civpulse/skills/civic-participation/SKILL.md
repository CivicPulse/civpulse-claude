---
name: civic-participation
description: Use when helping someone register or vote, contact officials, comment on a proposal, request public records, or otherwise take part in local government.
license: MIT
metadata:
  version: 1.0.0
  tags: [civic, participation, voting]
---

# Civic participation

Help people take effective, lawful, nonpartisan action in public life: getting
registered, finding what is on the ballot, contacting representatives, commenting
on proposals, and requesting records. Works from public sources and uses Civic
Pulse records to locate officials and meetings when available.

## When to use

- Check voter registration status, deadlines, or polling information.
- Find and contact the right official for an issue.
- Submit public comment on a proposal or permit.
- File a public records request.

## Core method

1. **Find the right door.** Match the issue to the level of government and the
   specific body: city, county, school district, state, or federal. Confirm the
   district and the current officeholder.
2. **Get the deadline from the authority.** Cite the election office, clerk, or
   agency page. Never guess a deadline.
3. **Use official channels.** Prefer the agency's portal, comment system, or
   published email and address over social media.
4. **Be specific and civil.** Identify yourself and your relevance (resident,
   business, parent), name the item (bill, agenda item, permit number) and its
   date, state your position with one reason, and ask for a reply.
5. **For records requests,** cite the applicable public records law, describe the
   records by type and date range, ask for electronic delivery, and keep the
   request proportionate.

## With the Civic Pulse MCP server

Use `search_people`/`get_person` to resolve an official and
`search_events`/`get_event` to find the meeting where an item will be heard when
`mcp__civpulse__*` tools are available. The MCP `search_users` tool is for
registered *accounts* and is unrelated to civic participation; do not use it to
look up members of the public.

## Guardrails

- Stay nonpartisan: never advise how to vote or whom to support.
- Do not collect or store sensitive personal data; use only the user's own
  details for their submission.
- Point to official sources and note that this is not legal advice.
- Do not fabricate deadlines, addresses, or procedure.

## Output

Give the concrete next action, the official channel or link, the deadline, and
anything the person must bring or prepare.
