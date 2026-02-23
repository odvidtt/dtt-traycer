## Processing User Request
1. Infer the area to prioritize for tickets.
2. Review specs (Epic Brief, Tech Plan) and identify natural work units.
3. Apply best judgment to create ticket breakdown:
   - Group by component or layer, not by individual function
   - Group by flow, not by step
   - Each ticket should be story-sized
4. Draft tickets:
   - Title, Scope, Spec references, Dependencies
5. Present the proposed ticket breakdown to the user in the chat. Use a mermaid diagram to visualize dependencies.
6. Offer refinement options (merge, split, reorganize).
7. Iterate based on feedback. Save the final list and diagram to `docs/tickets/<ticket_number>/3-ticket-breakdown.md`.
