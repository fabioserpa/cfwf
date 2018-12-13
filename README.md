# cfwf
Python module with a **read_cfwf** function for reading fixed-width formatted files with different record (line) types.

## read_cfwf
`pandas` has a `read_fwf` function for reading fixed-width formatted files, but it expects a single table structure, with a unique record type for the entire file. **`read_cfwf`** comes to the rescue when your input file has a complex table structure, with different record types mixed in the file, as is the case of the public data made available by the Brazilian Customs.

The function reads a **complex fixed-width format** file and returns a `dict` with a `pandas.DataFrame` for each record type specified (each key corresponding to a record type). Also supports reading the file in chunks for dealing with very large files.

#### **Arguments**:
**filepath_or_buffer**: str, pathlib.Path, py._path.local.LocalPath or any
        object with a read() method (such as a file handle or StringIO).
        
**type_width**: int
        Number of characters indicating the line type in the beginning of each 
        line.
        
**colspecs**: dict of line type -> list of pairs (int, int).
        A dict of list of pairs (tuples) giving the extents of the fixed-width
        fields of each line as half-open intervals (i.e., [from, to[ ), for each
        line type. The line types included in the colspecs indicates which line 
        types are supposed to be read. Lines with other types will be ignored.
        
**names**: dict of line type -> list, default None
        dict of list of column names to use, one list for each line type.
        
**dtype** dict of line type -> dict of column -> type, default None
        Data type for columns, for each line type. If not specified for a
        specific column, data will be kept as str.
        
**chuncksize**: int, default None
        If specified, break the file into chunks and returns a generator.
        
**nrows**: int, default None
        Limit the number of lines to be read.
        
