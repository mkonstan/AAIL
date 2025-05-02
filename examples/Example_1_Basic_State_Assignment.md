REMEMBER explicitGoals = selectGoals(promptRequirements)
IF explicitGoals EQ NULL THEN
    REPORT "Explicit goals missing."
END IF