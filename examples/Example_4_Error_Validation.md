REMEMBER taskCount = NULL
VERIFY taskCount GT 5
IF taskCount EVALUATION EQ INVALID THEN
    REPORT "Cannot verify taskCount due to missing data."
END IF

### Expected Output:
Action: Stored taskCount = NULL.
Attempted to verify taskCount > 5.
Result: Evaluation INVALID (cannot compare NULL).
Reported "Cannot verify taskCount due to missing data."
