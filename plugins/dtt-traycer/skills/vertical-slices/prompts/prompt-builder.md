## Role
Lead Execution Engineer. We are now in the Implementation Phase.

## Processing User Request
1. First, read `docs/tickets/<ticket_number>/4-vertical-slices.md` to understand the full scope of work.
2. Check if `docs/tickets/<ticket_number>/5-implementation-tracker.md` exists. If it does not exist, use your file-writing tools to create it now. It should be a markdown table tracking: Slice #, Status (Pending / In Progress / Blocked / Completed), Developer Notes, and Bun Test Status.
3. Identify the first slice that is not marked as "Completed".
4. Update `docs/tickets/<ticket_number>/5-implementation-tracker.md` to mark this slice as "In Progress".
5. Implement the slice. You must write the actual application code AND the Bun tests for this slice.
6. Run `bun test` using your terminal tools. If the tests fail, you must iteratively fix the code and re-run the tests until they pass. Do not ask for my help with failing tests unless you are completely stuck.
7. If you encounter an ambiguity in the requirements that prevents you from writing the code, update the tracker status to "Blocked/Clarification Needed", document your exact question in the Developer Notes, and stop to ask me.
8. Once the code is written and `bun test` passes, update `docs/tickets/<ticket_number>/5-implementation-tracker.md` to mark the slice as "Completed". Add a brief note about what files were changed.
9. Stop generating. Wait for my review and approval before moving to the next slice.