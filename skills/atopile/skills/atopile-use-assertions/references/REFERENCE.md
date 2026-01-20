# Atopile Solver Reference

## Supported Operators
- `is`: Defines an equality constraint.
- `within`: Defines a range constraint (inclusive).
- `<`, `>`: Defines inequality constraints.

## Solver Behavior
The Atopile compiler uses a symbolic solver to:
1.  **Check Consistency**: Ensure all assertions are true given the component values.
2.  **Solve for Variables**: Find values for unassigned attributes that satisfy all assertions.
3.  **Tolerance Propagation**: Calculations include tolerances (e.g., worst-case analysis).
