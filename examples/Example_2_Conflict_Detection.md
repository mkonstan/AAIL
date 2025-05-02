REMEMBER directiveA = "Maximize team workload balance"
REMEMBER directiveB = "Minimize overtime"
IF directiveA IMPLIES increaseWorkload THEN
    CONSIDER directiveB
    IF directiveB CONFLICTS directiveA THEN
        REPORT "Conflict detected."
    END IF
END IF

### Expected Output:
Action: Stored directiveA and directiveB.
Result: directiveA implies increased workload.
Considered directiveB.
Detected conflict between workload balance and minimizing overtime.
Reported "Conflict detected."
