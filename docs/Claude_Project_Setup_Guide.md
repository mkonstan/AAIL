# Claude Project Setup Guide v0.3-pre

## Setup Instructions
1. Define project instructions clearly (use Claude Project Instructions latest version).
2. Upload schema file (AAIL Schema Reference latest version).
3. Provide example directives if required.

## Using AAIL
- All reasoning actions defined using verbs: REMEMBER, VERIFY, EVAL, REPORT, CLARIFY.
- Use consistent syntax as defined in schema.

## Directive Testing
- Explicit invocation: `EVAL DIRECTIVE name REM RES RESULT`
- Implicit invocation: parsed automatically as EVAL commands.