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

Finally, you can emit an event using the `(emitWith <type> <value>)` function:
```lisp
(events_manager.emitWith "myType" 4)
```

Alternatively, if you wish to emit with no value, you can call `emit <type>` (which calls `emitWith <type> nil`)