
# AAIL Eval Block Syntax Cheat Sheet

## 🔹 Simple AAIL-Only Block (type declaration optional)

```plaintext
:start eval
    - IF x EQ y THEN
        - REPORT "x equals y."
:end eval
```

## 🔹 Multi-Format Block (type declaration required)

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

## 🔹 Format Declaration Rules

| Format | Body Header | Notes |
|---|---|---|
| YAML | `yaml:` | Structured data |
| Markdown | `Markdown:` | Human-readable comments |
| XML | `xml:` | Metadata, schema |
| AAIL | `AAIL:` | Reasoning logic (default if no header) |

**Default:** If `:start eval` has no types declared → assume **AAIL only**.
