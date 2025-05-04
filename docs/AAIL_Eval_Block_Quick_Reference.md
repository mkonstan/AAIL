# AAIL Eval Block Quick Reference v0.3-pre

## Multi-format Blocks
- YAML, Markdown, XML, AAIL allowed.

### Example Block
```
:start eval YAML, AAIL

yaml:
  threshold: 10

AAIL:
  REM count IS 5
  VERIFY count IS NOT threshold
  IF count IS NOT threshold THEN
      REPORT "Count below threshold."
  END IF
:end eval
```

## Directive Invocation
```
EVAL DIRECTIVE validateInput REM RES RESULT
```