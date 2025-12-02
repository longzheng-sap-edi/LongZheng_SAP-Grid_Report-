# ⚠️ Usage Notice
This repository is published solely for interview and technical demonstration. 
Commercial usage, including training materials or project implementation, is strictly prohibited.

# `Z_MM_LONG_001_GRID` - ABAP Report for Material Information Display


<img width="803" height="209" alt="image" src="https://github.com/user-attachments/assets/1325fe8e-18da-40be-ad97-daecf22a9310" />

<img width="502" height="433" alt="image" src="https://github.com/user-attachments/assets/bf6d3ad1-56c8-4c0f-96c7-2da45f4f918f" />


## Overview

The report `Z_MM_LONG_001_GRID` allows users to retrieve and display material data, including material number (`MATNR`), description (`MAKTX`), and material group (`MATKL`), from SAP's standard `MARA` and `MAKT` tables. The data is presented in an ALV (ABAP List Viewer) grid, where users can filter materials based on material number.

## Features

- **Material Data Display**: Displays material number, description, and material group in an interactive grid.
- **ALV Grid**: Uses the standard ALV grid functionality to display the data with sorting, filtering, and interactive capabilities.
- **Transaction Linking**: Clicking on the material number in the grid will take the user to the `MM03` transaction for detailed material information.

## Technical Details

- **Tables Used**:
  - `MARA`: Contains general material data.
  - `MAKT`: Contains material descriptions in various languages.
  
- **Type Definitions**:
  - A custom type `typ_mara` is used to structure the data for display, including `matnr` (Material Number), `maktx` (Description), and `matkl` (Material Group).
  
- **Selection Option**:
  - `s_matnr`: A selection field that allows the user to enter one or more material numbers for filtering the data.

- **ALV Display**:
  - The function `REUSE_ALV_GRID_DISPLAY` is used to display the data in an ALV grid. The layout and field catalog are dynamically created for material data display.
  
- **User Command Handling**:
  - When a user clicks on a material number (`MATNR`), the program triggers the `MM03` transaction to view the material details.

## How to Use

1. **Run the Report**:
   - Enter the material numbers you want to search for in the selection screen (`Material Number` field).
   - Press the "Execute" button to retrieve and display the material information in the ALV grid.

2. **Interact with the ALV Grid**:
   - The ALV grid provides sorting, filtering, and interactive features.
   - Click on a material number in the `MATNR` column to open the `MM03` transaction for that material.

## Example Usage

1. **Input**: 
   - Enter `1000001` for the material number in the selection screen.
2. **Output**: 
   - The ALV grid will display the material number `1000001`, its description, and material group.
   - Clicking on `1000001` will open the `MM03` material display transaction.

## Important Notes

- **Authorization**: Ensure that the user has the appropriate authorizations to view material master data and execute the `MM03` transaction.
- **Performance Considerations**: Large selections might impact performance; try to limit the input to a reasonable number of material numbers.
- **ALV Features**: The ALV grid allows users to export data, sort, and filter the displayed fields.

## Troubleshooting

- If the report does not return any data, ensure that the material numbers entered are valid and exist in the database.
- If the ALV grid does not display correctly, check the system configuration for ALV display settings.

## Future Enhancements

- Implement additional fields from the `MARA` and `MAKT` tables, such as material type, base unit of measure, etc.
- Provide export options to CSV or Excel formats.

