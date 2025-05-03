# AAIL — AI Agent Instruction Language

Declarative language for transparent, explainable AI reasoning.
Version: 0.1

## Structure
- schema/: YAML and XML schema
- benchmark/: Test results
- primer/: Few-shot example
- roadmap/: v0.2 plans
- examples/: Usage examples
- docs/: Full spec and schema reference

# AAIL v0.2-pre Summary

## 🎯 Version: v0.2-pre
## 📅 Date: May 2025
## 📚 Summary:
AAIL v0.2-pre introduces formal support for multi-format directives, explicit eval block format declarations, and best practices for transparent, explainable AI reasoning.

## 🔹 Key Features
✅ Eval block format declaration (:start eval YAML, Markdown, AAIL).  
✅ Default to AAIL logic if no format declared.  
✅ Segregated content headers (yaml:, Markdown:, xml:, AAIL:).  
✅ Updated schema, simple guide, primer, and Claude instructions.  
✅ New Quick Reference and Best Practices guides.  
✅ Improved clarity, parser friendliness, and future extensibility.

## 🔹 Example

```plaintext
:start eval YAML, Markdown, AAIL

yaml:
  threshold: 10

Markdown:
  ## Purpose
  Evaluate if value exceeds threshold.

AAIL:
    - IF value GT threshold THEN
        - REPORT "Value exceeds threshold."
:end eval
```

## 🔹 New Files

| File | Purpose |
|---|---|
| AAIL_Eval_Block_Quick_Reference.md | Cheat sheet for eval block syntax |
| AAIL_Best_Practices.md | Guidance for writing high-quality directives |

## 🔹 Example Directive Included
- directives/example_directive_1.aail
