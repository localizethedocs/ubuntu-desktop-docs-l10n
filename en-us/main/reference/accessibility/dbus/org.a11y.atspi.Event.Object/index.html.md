# org.a11y.atspi.Event.Object

## Description

## Signals

### org.a11y.atspi.Event.Object::PropertyChange

```none
PropertyChange (
  property s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  value v,
  properties a{sv}
)
```

property

unnamed_arg1

unnamed_arg2

value

properties

### org.a11y.atspi.Event.Object::BoundsChanged

```none
BoundsChanged (
  unnamed_arg0 s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

unnamed_arg1

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::LinkSelected

```none
LinkSelected (
  unnamed_arg0 s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

unnamed_arg1

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::StateChanged

```none
StateChanged (
  state s,
  enabled i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

state

enabled

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::ChildrenChanged

```none
ChildrenChanged (
  operation s,
  index_in_parent i,
  unnamed_arg2 i,
  child v,
  properties a{sv}
)
```

operation

index_in_parent

unnamed_arg2

child

properties

### org.a11y.atspi.Event.Object::VisibleDataChanged

```none
VisibleDataChanged (
  unnamed_arg0 s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

unnamed_arg1

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::SelectionChanged

```none
SelectionChanged (
  unnamed_arg0 s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

unnamed_arg1

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::ModelChanged

```none
ModelChanged (
  unnamed_arg0 s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

unnamed_arg1

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::ActiveDescendantChanged

```none
ActiveDescendantChanged (
  unnamed_arg0 s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  child v,
  properties a{sv}
)
```

unnamed_arg0

unnamed_arg1

unnamed_arg2

child

properties

### org.a11y.atspi.Event.Object::Announcement

```none
Announcement (
  unnamed_arg0 s,
  politeness i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

politeness

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::AttributesChanged

```none
AttributesChanged (
  name s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

name

unnamed_arg1

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::RowInserted

```none
RowInserted (
  unnamed_arg0 s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

unnamed_arg1

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::RowReordered

```none
RowReordered (
  unnamed_arg0 s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

unnamed_arg1

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::RowDeleted

```none
RowDeleted (
  unnamed_arg0 s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

unnamed_arg1

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::ColumnInserted

```none
ColumnInserted (
  unnamed_arg0 s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

unnamed_arg1

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::ColumnReordered

```none
ColumnReordered (
  unnamed_arg0 s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

unnamed_arg1

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::ColumnDeleted

```none
ColumnDeleted (
  unnamed_arg0 s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

unnamed_arg1

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::TextBoundsChanged

```none
TextBoundsChanged (
  unnamed_arg0 s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

unnamed_arg1

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::TextSelectionChanged

```none
TextSelectionChanged (
  unnamed_arg0 s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

unnamed_arg1

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::TextChanged

```none
TextChanged (
  detail s,
  start_pos i,
  length i,
  text v,
  properties a{sv}
)
```

detail

start_pos

length

text

properties

### org.a11y.atspi.Event.Object::TextAttributesChanged

```none
TextAttributesChanged (
  unnamed_arg0 s,
  unnamed_arg1 i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

unnamed_arg1

unnamed_arg2

unnamed_arg3

properties

### org.a11y.atspi.Event.Object::TextCaretMoved

```none
TextCaretMoved (
  unnamed_arg0 s,
  position i,
  unnamed_arg2 i,
  unnamed_arg3 v,
  properties a{sv}
)
```

unnamed_arg0

position

unnamed_arg2

unnamed_arg3

properties
