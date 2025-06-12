# Import Layer Structure from 3DM Template in Rhino3D

Automatically replicate complex, nested layer structures from another Rhino file. This custom script is ideal for architectural workflows requiring standardised templates across multiple files or teams.

## What Does It Do?

The **Recursive Layer Import Tool** allows you to:

* Select a Rhino `.3dm` file that contains a predefined layer structure.
* Read and replicate all layers, including colours, line types, and visibility.
* Preserve nested sublayer hierarchies by rebuilding them recursively in the current document.

This ensures consistency and efficiency when setting up files for large projects or office-wide standards.

## Why Use This Script?

Setting up layers manually across projects is tedious and error-prone. Rhino’s built-in layer import does not always preserve hierarchy or selectively import from files without importing geometry. This tool:

* Automates clean and precise transfer of layer templates.
* Keeps layer hierarchies fully intact.
* Avoids geometry imports or unwanted file content.

## How to Use the Script

### Load the Script in Rhino

**Method 1**:

1. Type `_RunPythonScript` in the command line.
2. Browse to the saved location of the script and run it.

### Method 2 Creating a Button or Alias (Optional)

#### Toolbar Button

1. **Right-click** an empty area of the toolbar and choose **New Button**.
2. In the **Button Editor**:

   * **Left Button Command**:

     ```plaintext
     ! _-RunPythonScript "FullPathToYourScript\import_layers_recursive.py"
     ```

     Replace `FullPathToYourScript` with the actual path to your script.
   * **Tooltip**: e.g., `Import layer structure from template file`.

#### Command Alias

1. Open **Tools > Options > Aliases**.
2. Add a new alias, for example:

   * **Alias**: `layerimport`
   * **Macro**:

     ```plaintext
     _-RunPythonScript "FullPathToYourScript\import_layers_recursive.py"
     ```

### Using the Tool

1. Run the script via command line, button, or alias.
2. **Select a Rhino `.3dm` file** that contains the desired layer structure.
3. The script will:

   * Parse the layer tree.
   * Reconstruct all layers and nested sublayers into the current file.
   * Maintain properties like colour, linetype, visibility, lock state, and hierarchy.

### What Gets Imported

* Layer names and nesting
* Layer colours
* Plot colours
* Linetypes
* Visibility and lock states

### What Does *Not* Get Imported

* Geometry
* Layer materials
* Layouts or model space contents

This ensures only the structural layer system is brought into your active model.
