# Atopile Component Reference

## Global Attributes
- `lcsc_id`: The LCSC part number (e.g., "C11702"). Forces the picker to use this part.
- `mpn`: Manufacturer Part Number.
- `manufacturer`: Exact name of the manufacturer.
- `package`: Footprint package name (e.g., "0402", "SOT-23-5").
- `exclude_from_bom`: Boolean to hide the part from the Bill of Materials.

## Component Picker
If `lcsc_id` or `mpn` is not set, the Atopile compiler will automatically pick a part that satisfies all constraints (resistance, voltage, package, etc.).
