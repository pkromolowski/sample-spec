## Overview

This COBOL code pattern demonstrates a simple application that reads data from three input files, merges them into a single sorted list, and writes the sorted list to an output file. The code showcases basic file handling, data manipulation, and sorting capabilities in COBOL.

## Package/module name

-  `cobol-is-fun` (Based on the repository name)

## Class/file name

-  `my-first-program.cbl` (Based on the code description)

## Detailed Documentation

### Function/Method: `READ_DATA`

- **Description:** Reads data from a specified input file and stores it in a data structure.
- **Parameters:**
    - `filename` (STRING): The name of the input file to read from.
- **Return Values:**
    - `data_list` (ARRAY OF STRING): An array containing the data read from the file.
- **Important Logic:**
    - Opens the specified input file for reading.
    - Reads each line from the file and stores it as a string in the `data_list` array.
    - Closes the input file.

### Function/Method: `MERGE_DATA`

- **Description:** Merges data from multiple input data lists into a single sorted list.
- **Parameters:**
    - `data_list1` (ARRAY OF STRING): The first data list to merge.
    - `data_list2` (ARRAY OF STRING): The second data list to merge.
    - `data_list3` (ARRAY OF STRING): The third data list to merge.
- **Return Values:**
    - `merged_data` (ARRAY OF STRING): A sorted array containing all the merged data.
- **Important Logic:**
    - Combines the three input data lists into a single list.
    - Sorts the combined list alphabetically.

### Function/Method: `WRITE_DATA`

- **Description:** Writes the sorted data to an output file.
- **Parameters:**
    - `merged_data` (ARRAY OF STRING): The sorted data to write to the file.
    - `output_filename` (STRING): The name of the output file.
- **Return Values:**
    - None
- **Important Logic:**
    - Opens the specified output file for writing.
    - Writes each element of the `merged_data` array to the file, one per line.
    - Closes the output file.

## Pseudo Code

1. **Initialize:**
    - Declare variables for input and output filenames.
    - Declare arrays to store data from each input file.
2. **Read Data:**
    - Call `READ_DATA` function for each input file, passing the filename as a parameter.
    - Store the returned data arrays in respective variables.
3. **Merge Data:**
    - Call `MERGE_DATA` function, passing the three data arrays as parameters.
    - Store the returned sorted data array in `merged_data`.
4. **Write Data:**
    - Call `WRITE_DATA` function, passing the `merged_data` array and the output filename as parameters.
5. **End:**
    - Program execution completes.

**Edge Cases and Error Handling:**

- **File Not Found:** Implement error handling to catch cases where input or output files cannot be found.
- **Invalid Data Format:** Implement validation logic to ensure that the data read from files adheres to the expected format.
- **Memory Allocation Errors:** Handle potential memory allocation errors during data processing.



**Dependencies and Libraries:**

- **COBOL Compiler:** IBM Enterprise COBOL or equivalent COBOL compiler.
- **Operating System:** z/OS or equivalent mainframe operating system.
- **JCL:** Job Control Language for executing the COBOL program.



