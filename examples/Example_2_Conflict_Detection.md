REMEMBER directiveA = "Maximize team workload balance"
REMEMBER directiveB = "Minimize overtime"
IF directiveA IMPLIES increaseWorkload THEN
    CONSIDER directiveB
    IF directiveB CONFLICTS directiveA THEN
        REPORT "Conflict detected."
    END IF
END IF