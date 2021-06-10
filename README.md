# arkscript-events
A small ArkScript lib for events emitting/listening

## Description
First of all, create the events manager using the `make_eventsManager` closure
```lisp
(let events_manager (events:manager:make))
```

Then, you can register an event listener using the `(on <type> <callback>)` function (your callback function needs exactly one parameter):
```lisp
(events_manager.on "myType" (fun (param) (print "Caught event of type myType with parameter " param)))
```
This registers an event that listens for the type "myType" and prints something to the console when an event of said type is emitted.

Finally, you can emit an event using the `(emitWith <value> <type>)` function:
```lisp
(events_manager.emitWith 4 "myType")
```
Alternatively, if you wish to emit with no value, you can call `emit <type>` (which calls `emitWith nil <type>`)

If you wish to delete listeners, you can use `(removeListenersOfType <type>)`:
```lisp
(removeListenersOfType "myType")
```

If you want to see the return values, or how it works, check out the `events/Event.ark` file.