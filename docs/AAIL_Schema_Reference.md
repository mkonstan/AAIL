# AAIL Schema Reference v0.3-pre

## Verb Families
- Memory: REMEMBER (REM), RECALL
- Decision: VERIFY, IMPLIES, MATCH, LIKE
- Imperative: EVAL
- Transparency: REPORT, CLARIFY

## Operators
- IS (assignment, equality)
- IS NOT (inequality, only in IF statements)
- REM RES (optional result capture, stores directive/task outcomes)

## Directive Invocation
- Explicit: EVAL DIRECTIVE <name> [REM RES RESULT]
- Implicit: Directive-like inputs parsed into EVAL commands

## Reserved Keywords
- RESULT (RES) (exclusively for directive/task outcomes or explicit assignment via REMEMBER)

## Deprecated Verbs
- EVALUATE, EXECUTE DIRECTIVE, INTERPRET DIRECTIVE, CACHE, FORGET
- FILTER, SELECT, COUNT, SUM, EXISTS

## Example
```
EVAL DIRECTIVE workloadCheck REM RES RESULT
IF RESULT IS NOT "OK" THEN
    REPORT "Workload check failed."
END IF
```