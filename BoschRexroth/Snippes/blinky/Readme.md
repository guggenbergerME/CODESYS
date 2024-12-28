# blinky

Einen Ausgang mit einer bestimmten Frequenz blinken lassen.

```
VAR
timer : TON;
t : time := T#200ms;
END_VAR

timer(PT:=t,IN:=not timer.Q);

Ausgang := timer.ET < timer.PT/2;
```

