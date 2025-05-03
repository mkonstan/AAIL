
# 🔥 Best Practices for Writing Eval Blocks

## ✅ Always:
- Use **format declarations** when combining YAML, Markdown, XML with AAIL.
- Keep section headers clear (`yaml:`, `Markdown:`, `xml:`, `AAIL:`).
- Comment purposes and logic inside Markdown sections for human readers.
- Validate YAML or XML against your intended schema (if applicable).
- Align AAIL verbs with the official schema list (REMEMBER, RECALL, VERIFY, EVALUATE, CONSIDER, REPORT).

## ⚡ Optional (for advanced use):
- Nest directives inside eval blocks if future versions allow.
- Use REPORT statements for transparency, even in complex logic.
- Keep YAML and XML data minimal — avoid overwhelming the logic block.
- Keep eval blocks modular — break down complex reasoning into multiple directives if needed.

## 📝 Example: Full Mixed Directive

```plaintext
# Resource allocation conflict check
DIRECTIVE: resourceConflictCheck

:start eval YAML, Markdown, AAIL

yaml:
  maxAllocation: 100
  currentUsage: 110

Markdown:
  ## Purpose
  Checks if current resource usage exceeds the allowed maximum.

AAIL:
    - IF currentUsage GT maxAllocation THEN
        - REPORT "Resource over-allocation detected."
    - ELSE
        - REPORT "Usage within limits."
:end eval
```
