## Overview

This COBOL application demonstrates data processing by reading data from three input files, merging them into a single list, sorting the merged list, and writing the sorted list to an output file. 

## Package/module name

This code doesn't appear to be organized into packages or modules in the traditional sense. It's a single COBOL program.

## Class/file name

The source code file is named `fxsort.cbl`.

## Detailed Documentation

### `PROCESS-RECORDS`

- **Description:** This procedure performs the core functionality of the program: merging input files and sorting the merged data.
- **Parameters:** None
- **Return Values:** None
- **Important Logic:**
    - It first displays "MERGING FILES" to the console.
    - It uses the `MERGE` statement to combine data from three input files (`FXLIST-B`, `FXLIST-M`, `FXLIST-J`) into a temporary file (`FXLIST-MERGE`). The merge operation is performed based on the ascending order of the `FX-NAME-W` field in the `FX-REC` record.
    - It then displays "SORTING RECORDS" to the console.
    - It uses the `SORT` statement to sort the data in `FXLIST-MERGE` based on the ascending order of the `FX-PRICE-W` field in the `FX-REC` record. The sorted data is written to an output file (`FXLIST-SORTED`).

### `CLOSE-STOP`

- **Description:** This procedure handles program termination.
- **Parameters:** None
- **Return Values:** None
- **Important Logic:**
    - It displays "NOW I'M STOPPING" to the console.
    - It uses the `STOP RUN` statement to terminate the program execution.

## Data Structures

- **`FX-REC`:** This record structure defines the format of records read from and written to the input and output files. It contains fields for `FX-NAME-W` (name), `FX-PRICE-W` (price), and a `FILLER` field.

- **`FX-MERG`:** This record structure is used during the merging process. It has fields for `FX-NAME-M`, `FX-PRICE-M`, and a `FILLER` field.

- **`PRINT-REC`:** This record structure is used during the sorting process. It has fields for `FX-NAME-S`, `FX-PRICE-S`, and a `FILLER` field.

- **`BOSS-FIELDS`:** This record structure is used for reading data from the `FXLIST-B` file.

- **`MXR-FIELDS`:** This record structure is used for reading data from the `FXLIST-M` file.

- **`JHS-FIELDS`:** This record structure is used for reading data from the `FXLIST-J` file.

## Dependencies and Libraries

- This code relies on the COBOL compiler and runtime environment provided by the z/OS operating system.

## Pseudo Code

1. **Display "MERGING FILES"**
2. **Merge data from `FXLIST-B`, `FXLIST-M`, and `FXLIST-J` into `FXLIST-MERGE` based on ascending order of `FX-NAME-W` in `FX-REC` record.**
3. **Display "SORTING RECORDS"**
4. **Sort data in `FXLIST-MERGE` based on ascending order of `FX-PRICE-W` in `FX-REC` record, writing the sorted data to `FXLIST-SORTED`.**
5. **Display "NOW I'M STOPPING"**
6. **Terminate program execution.**



