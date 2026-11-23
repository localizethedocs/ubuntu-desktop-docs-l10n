# org.a11y.atspi.Table

## Description

## Properties

### org.a11y.atspi.Table:NRows

```none
NRows readable i
```

### org.a11y.atspi.Table:NColumns

```none
NColumns readable i
```

### org.a11y.atspi.Table:Caption

```none
Caption readable (so)
```

### org.a11y.atspi.Table:Summary

```none
Summary readable (so)
```

### org.a11y.atspi.Table:NSelectedRows

```none
NSelectedRows readable i
```

### org.a11y.atspi.Table:NSelectedColumns

```none
NSelectedColumns readable i
```

## Methods

### org.a11y.atspi.Table.GetAccessibleAt

```none
GetAccessibleAt (
  IN row i,
  IN column i,
  OUT unnamed_arg2 (so)
)
```

row

column

unnamed_arg2

### org.a11y.atspi.Table.GetIndexAt

```none
GetIndexAt (
  IN row i,
  IN column i,
  OUT unnamed_arg2 i
)
```

row

column

unnamed_arg2

### org.a11y.atspi.Table.GetRowAtIndex

```none
GetRowAtIndex (
  IN index i,
  OUT unnamed_arg1 i
)
```

index

unnamed_arg1

### org.a11y.atspi.Table.GetColumnAtIndex

```none
GetColumnAtIndex (
  IN index i,
  OUT unnamed_arg1 i
)
```

index

unnamed_arg1

### org.a11y.atspi.Table.GetRowDescription

```none
GetRowDescription (
  IN row i,
  OUT unnamed_arg1 s
)
```

row

unnamed_arg1

### org.a11y.atspi.Table.GetColumnDescription

```none
GetColumnDescription (
  IN column i,
  OUT unnamed_arg1 s
)
```

column

unnamed_arg1

### org.a11y.atspi.Table.GetRowExtentAt

```none
GetRowExtentAt (
  IN row i,
  IN column i,
  OUT unnamed_arg2 i
)
```

row

column

unnamed_arg2

### org.a11y.atspi.Table.GetColumnExtentAt {#org.a11y.atspi.Table.GetColumnExtentAt}

```none
GetColumnExtentAt (
  IN row i,
  IN column i,
  OUT unnamed_arg2 i
)
```

row

column

unnamed_arg2

### org.a11y.atspi.Table.GetRowHeader {#org.a11y.atspi.Table.GetRowHeader}

```none
GetRowHeader (
  IN row i,
  OUT unnamed_arg1 (so)
)
```

row

unnamed_arg1

### org.a11y.atspi.Table.GetColumnHeader {#org.a11y.atspi.Table.GetColumnHeader}

```none
GetColumnHeader (
  IN column i,
  OUT unnamed_arg1 (so)
)
```

column

unnamed_arg1

### org.a11y.atspi.Table.GetSelectedRows {#org.a11y.atspi.Table.GetSelectedRows}

```none
GetSelectedRows (
  OUT unnamed_arg0 ai
)
```

unnamed_arg0

### org.a11y.atspi.Table.GetSelectedColumns {#org.a11y.atspi.Table.GetSelectedColumns}

```none
GetSelectedColumns (
  OUT unnamed_arg0 ai
)
```

unnamed_arg0

### org.a11y.atspi.Table.IsRowSelected {#org.a11y.atspi.Table.IsRowSelected}

```none
IsRowSelected (
  IN row i,
  OUT unnamed_arg1 b
)
```

row

unnamed_arg1

### org.a11y.atspi.Table.IsColumnSelected {#org.a11y.atspi.Table.IsColumnSelected}

```none
IsColumnSelected (
  IN column i,
  OUT unnamed_arg1 b
)
```

column

unnamed_arg1

### org.a11y.atspi.Table.IsSelected {#org.a11y.atspi.Table.IsSelected}

```none
IsSelected (
  IN row i,
  IN column i,
  OUT unnamed_arg2 b
)
```

row

column

unnamed_arg2

### org.a11y.atspi.Table.AddRowSelection {#org.a11y.atspi.Table.AddRowSelection}

```none
AddRowSelection (
  IN row i,
  OUT unnamed_arg1 b
)
```

row

unnamed_arg1

### org.a11y.atspi.Table.AddColumnSelection {#org.a11y.atspi.Table.AddColumnSelection}

```none
AddColumnSelection (
  IN column i,
  OUT unnamed_arg1 b
)
```

column

unnamed_arg1

### org.a11y.atspi.Table.RemoveRowSelection {#org.a11y.atspi.Table.RemoveRowSelection}

```none
RemoveRowSelection (
  IN row i,
  OUT unnamed_arg1 b
)
```

row

unnamed_arg1

### org.a11y.atspi.Table.RemoveColumnSelection {#org.a11y.atspi.Table.RemoveColumnSelection}

```none
RemoveColumnSelection (
  IN column i,
  OUT unnamed_arg1 b
)
```

column

unnamed_arg1

### org.a11y.atspi.Table.GetRowColumnExtentsAtIndex {#org.a11y.atspi.Table.GetRowColumnExtentsAtIndex}

```none
GetRowColumnExtentsAtIndex (
  IN index i,
  OUT unnamed_arg1 b,
  OUT row i,
  OUT col i,
  OUT row_extents i,
  OUT col_extents i,
  OUT is_selected b
)
```

index

unnamed_arg1

row

col

row_extents

col_extents

is_selected
