REMEMBER taskCount = NULL
VERIFY taskCount GT 5
IF taskCount EVALUATION EQ INVALID THEN
    REPORT "Cannot verify taskCount due to missing data."
END IF