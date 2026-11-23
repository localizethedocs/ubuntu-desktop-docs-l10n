# org.a11y.atspi.TableCell

## Properties[]{#org.a11y.atspi.TableCell Description} {#org.a11y.atspi.TableCell Properties}

### org.a11y.atspi.TableCell:ColumnSpan {#org.a11y.atspi.TableCell:ColumnSpan}

```none
ColumnSpan readable i
```

### org.a11y.atspi.TableCell:Position {#org.a11y.atspi.TableCell:Position}

```none
Position readable (ii)
```

### org.a11y.atspi.TableCell:RowSpan {#org.a11y.atspi.TableCell:RowSpan}

```none
RowSpan readable i
```

### org.a11y.atspi.TableCell:Table {#org.a11y.atspi.TableCell:Table}

```none
Table readable (so)
```

## Methods {#org.a11y.atspi.TableCell Methods}

### org.a11y.atspi.TableCell.GetRowColumnSpan {#org.a11y.atspi.TableCell.GetRowColumnSpan}

```none
GetRowColumnSpan (
  OUT unnamed_arg0 b,
  OUT row i,
  OUT col i,
  OUT row_extents i,
  OUT col_extents i
)
```

unnamed_arg0

row

col

row_extents

col_extents

### org.a11y.atspi.TableCell.GetColumnHeaderCells {#org.a11y.atspi.TableCell.GetColumnHeaderCells}

```none
GetColumnHeaderCells (
  OUT unnamed_arg0 a(so)
)
```

Returns a list of the table cell’s column header cells.

unnamed_arg0

### org.a11y.atspi.TableCell.GetRowHeaderCells {#org.a11y.atspi.TableCell.GetRowHeaderCells}

```none
GetRowHeaderCells (
  OUT unnamed_arg0 a(so)
)
```

Returns a list of the table cell’s row header cells.

unnamed_arg0
