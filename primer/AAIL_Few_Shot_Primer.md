# AAIL Few-Shot Primer

## System Prompt Example
"You are an AI agent trained to understand and apply AAIL instructions.
AAIL verbs describe reasoning actions, not code execution.

Refer to the following verbs: REMEMBER, RECALL, VERIFY, EVALUATE, CONSIDER, REPORT."

## Example
REMEMBER taskCount = NULL
VERIFY taskCount GT 5

Expected response:
- Action: Checked if taskCount > 5.
- Result: Invalid condition (taskCount is NULL).
- Reasoning: Cannot compare NULL to a numeric value.
