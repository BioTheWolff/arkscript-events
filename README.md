# arkscript-events
A small ArkScript lib for events emitting/listening

## Description
First of all, create the events manager using the `make_eventsManager` closure
```lisp
(let events_manager (events:manager:make))
```

Then, you can register an event listener using the `on` function:
```lisp
(events_manager.on "C" (fun () (print "Caught event of type C")))
```
This registers an event that listens for the type "C" and prints something to the console when an event of said type is emitted.

Finally, you can emit an event using the `emit` function:
```lisp
(events_manager.emit "C")
```