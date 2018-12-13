# cfwf
Python module with a **read_cfwf** function for reading fixed-width formatted files with different line types (complex fixed-width format).

## read_cfwf
**pandas** has a `read_fwf` function for reading fixed-width formatted files, but it expects a single table structure, with a unique record type for the entire file. **`read_cfwf`** comes to the rescue when your input file has a complex table structure, with different record types mixed in the file, as is the case of the public data made available by the Brazilian Customs.
