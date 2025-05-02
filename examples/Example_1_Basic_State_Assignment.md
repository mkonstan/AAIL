REMEMBER explicitGoals = selectGoals(promptRequirements)
IF explicitGoals EQ NULL THEN
    REPORT "Explicit goals missing."
END IF

### Expected Output:
Action: Stored explicitGoals from prompt requirements.
Result: explicitGoals contains selected goals OR NULL.
If NULL, reported "Explicit goals missing."
