# AAIL Simple Guide v0.3-pre

## What is AAIL?

AAIL (AI Agent Instruction Language) provides clear, structured instructions to AI agents, similar to step-by-step directions you might give someone to perform a task accurately.

## Core Commands & Usage

### REMEMBER (REM)

Stores or assigns a value.

```
REM favoriteColor IS "blue"
```

### RECALL

Retrieves a previously stored value.

```
REM petName IS "Fluffy"
RECALL petName
```

### VERIFY

Checks if a condition is true or false.

```
REM playerAge IS 14
VERIFY playerAge IS 14
```

### EVAL

Executes a directive or task.

```
EVAL DIRECTIVE checkWeather REM RES RESULT
```

### REPORT

Outputs transparent reasoning or messages.

```
REPORT "Player has won the game."
```

### CLARIFY

Requests additional clarity or information.

```
CLARIFY "Could you specify the meeting time?"
```

## Operators

* **IS**: Used for assignment or equality comparison

  ```
  REM status IS "completed"
  IF status IS "completed" THEN REPORT "Task done." END IF
  ```

* **IS NOT**: Used for inequality comparisons only within IF statements

  ```
  IF status IS NOT "completed" THEN REPORT "Task not completed." END IF
  ```

* **REM RES**: Optionally captures results from EVAL

  ```
  EVAL DIRECTIVE analyzeData REM RES RESULT
  ```

## Conditional Logic

### IF, THEN, ELSE

Conditional branching based on logical evaluations.

```
REM temperature IS 32
IF temperature IS NOT 30 THEN
    REPORT "Temperature differs from expected."
ELSE
    REPORT "Temperature matches the expected value."
END IF
```

### MATCH

Checks exact equality in conditional logic.

```
REM email IS "user@example.com"
IF email MATCH "user@example.com" THEN REPORT "Email matches." END IF
```

### LIKE

Checks pattern similarity or partial matches.

```
REM message IS "Hello, world!"
IF message LIKE "%world%" THEN REPORT "Message contains 'world'." END IF
```

### IMPLIES

Logical consequence check within conditional logic.

```
REM isRaining IS TRUE
REM hasUmbrella IS TRUE
VERIFY isRaining IMPLIES hasUmbrella
```

## Deprecated Commands

The following commands have been deprecated and should no longer be used:

* EVALUATE
* EXECUTE DIRECTIVE
* INTERPRET DIRECTIVE
* CACHE
* FORGET
* FILTER
* SELECT
* COUNT
* SUM
* EXISTS

## Directive Example

```
EVAL DIRECTIVE workloadConflictResolution REM RES RESULT

IF RESULT IS "conflict" THEN
    REPORT "Conflict detected between workload balance and overtime."
ELSE
    REPORT "No conflicts detected."
END IF
```

## Handling NULL or Undefined Values

As of AAIL v0.3-pre, evaluations involving NULL, UNDEFINED, or undetermined values result in INVALID evaluation state.

```
REM taskCount IS NULL
VERIFY taskCount IS NOT NULL
```

**Expected Output:**

* Action: Checked if taskCount is not NULL
* Result: INVALID
* Reasoning: taskCount is NULL, evaluation state is INVALID

## Eval Block Format Declaration

Declare multiple formats clearly:

```
:start eval YAML, Markdown, AAIL

YAML:
  threshold: 10

Markdown:
  ## Analysis Goal
  Evaluate task completion.

AAIL:
  REM tasksCompleted IS 7
  VERIFY tasksCompleted IS NOT threshold
  IF tasksCompleted IS NOT threshold THEN
      REPORT "Tasks completed differ from threshold."
  END IF
:end eval
```

This updated guide clearly and consistently reflects the latest syntax and command structures for AAIL v0.3-pre.
