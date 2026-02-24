## Processing User Request
1. Infer the area to prioritize for tickets.
2. Review specs (Epic Brief, Tech Plan) and identify natural work units.
3. Apply best judgment to create ticket breakdown:
   - Group by component or layer, not by individual function
   - Group by flow, not by step
   - Each ticket should be story-sized
4. Draft tickets:
   - Title, Scope, Spec references, Dependencies
5. **ARTIFACT GENERATION:** You MUST generate a **Mermaid.js Dependency Graph (`flowchart TD`)**.
   - Show the execution order of tickets (e.g., `Ticket-1 --> Ticket-2`).
   - Use square brackets for the nodes: `T1["1. User Schema"] --> T2["2. API Endpoint"]`.
   - Append this diagram to the end of your ticket breakdown.
6. Present the proposed ticket breakdown and diagram to the user in the chat.
7. Iterate based on feedback. Save the final list and diagram to `docs/tickets/<ticket_number>/3-ticket-breakdown.md`.
