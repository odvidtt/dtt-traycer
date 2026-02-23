# Elephant Carpaccio v2.0 - Enhanced Slicing Methodology

## What is Elephant Carpaccio?

Breaks large projects into thin, vertical slices. Each slice is Implementable (< 1 day), Demonstrable, Valuable, and Vertical (UI -> API -> Data).

## New Slicing Techniques

1. **Zero-One-Many**: Empty states -> one item -> collections
2. **Hardcoded to Dynamic**: Static logic -> dynamic
3. **ZOMBIES**: Happy Path First
4. **Input/Data Slicing**: Increment complexity by data inputs
5. **Walking Skeleton to Meat to Skin**: Connect data flow -> business rules -> UI polish
6. **Operation Slicing (CRUD)**: Create -> Read -> Update -> Delete
7. **Test-First Slice**: Write test before implementing

## Slice Validation Rules

1. Time Box: Implementable in 2-4 hours
2. Observable: Demonstrable change
3. Valuable: More valuable than the last
4. Complete: Not just UI or API alone
5. Vertical: Cuts through ALL layers
6. Testable: Can be verified

**If a slice is estimated > 1 day, slice it further.**
