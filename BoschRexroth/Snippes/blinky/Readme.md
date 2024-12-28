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

## FUNCTION_BLOCK TON

Implements a timer with a turn-on delay
```
(* Example declaration *)
TONinstanzNAME : TON ;

(* Example in ST *)
TONInst(IN := VarBOOL1, PT:= T#5s);
VarBOOL2 := TONInst.Q;
```
Kürzel
```
IN    BOOL    Steigende Flanke / Fallende Flanke
PT    TIME    Zeit in ms
Q     BOOL    FALSE, wenn IN FALSE ist TRUE, wenn IN TRUE ist und die Verzögerungszeit PT verstrichen ist
ET    TIME    Verstrichene Zeit seit steigender Flanke an IN

```
