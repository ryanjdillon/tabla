tabla
=====

Generate LaTeX tables in Python.

Example
-------

::code:python
    import pandas as pd
    from tabla import TableColumn, Table

    # The data to generate a table from
    df = pd.DataFrame()

    # Information about your table columns
    # Each column name should corresond to a named column in your DataFrame.
    columns = [
        TableColumn("col_a", "m/s", "{0:0.2f}", "Wind Speed"),
        ]

    table = Table("my_table", columns, df)

    # Generate as a string
    print(table.dumps())

    # Write to .tex file
    table.dump("./my_table.tex")

    # Write as an image file
    table.compile("./my_table.png")
