# Atopile Layout Synchronization Reference

## Reusing Package Layouts

To reuse a layout from an imported package (e.g., `rp2040`):

1.  Ensure the package's module (e.g., `RP2040Kit`) is instantiated in your code.
2.  Run `ato build`.
3.  In KiCAD, use the **Atopile KiCAD plugin** to:
    *   Hit the "Sync Group" button.
    *   Select the group to sync.
    *   Hit the "Pull" (Down arrow) button to pull the layout from the module's KiCAD file.

## Creating Reusable Layouts

To create a reusable layout for your own module:

1.  Add a new build configuration with `ato create build`.
2.  Point the newly created entry at the module you want to have a reusable layout.
3.  Lay out the module in KiCAD. The layout will be saved and associated with that module.
