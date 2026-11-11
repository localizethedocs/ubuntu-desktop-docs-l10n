# org.a11y.atspi.Registry

## Description

## Methods

### org.a11y.atspi.Registry.RegisterEvent

```none
RegisterEvent (
  IN event s,
  IN properties as,
  IN app_bus_name s
)
```

event

properties

app_bus_name

### org.a11y.atspi.Registry.DeregisterEvent

```none
DeregisterEvent (
  IN event s
)
```

event

### org.a11y.atspi.Registry.GetRegisteredEvents

```none
GetRegisteredEvents (
  OUT events a(ss)
)
```

events

## Signals

### org.a11y.atspi.Registry::EventListenerRegistered

```none
EventListenerRegistered (
  bus s,
  path s
)
```

bus

path

### org.a11y.atspi.Registry::EventListenerDeregistered

```none
EventListenerDeregistered (
  bus s,
  path s
)
```

bus

path
