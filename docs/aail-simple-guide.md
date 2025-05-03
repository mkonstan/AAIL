
## Update Notice (AAIL v0.2-pre)
As of AAIL version 0.2-pre, any evaluation of a NULL, UNDEFINED, or undetermined value will result in the evaluation state INVALID.
This applies to all uses of VERIFY and EVALUATE.

# AAIL Simple Guide: Commands & Examples

## What is AAIL?

AAIL (AI Agent Instruction Language) is like a special language that helps AI understand step-by-step thinking. Think of it like giving very clear directions to a friend who needs to know exactly what to do.

## Basic Commands

### REMEMBER

This command helps the AI remember information. It's like writing something down so you don't forget it.

```
REMEMBER favoriteColor = "blue"
```

**Expected Output:**
- Action: Stored value "blue" in variable favoriteColor
- Result: Variable favoriteColor = "blue"
- Reasoning: Information has been saved for later use

### RECALL

This command helps the AI bring back information it stored earlier.

```
REMEMBER petName = "Fluffy"
RECALL petName
```

**Expected Output:**
- Action: Retrieved value from variable petName
- Result: "Fluffy"
- Reasoning: Successfully recalled stored information

### CACHE

This is like a short-term memory - it stores information temporarily.

```
CACHE tempScore = 85
```

**Expected Output:**
- Action: Temporarily stored value 85 in variable tempScore
- Result: Temporary variable tempScore = 85
- Reasoning: Value is stored for short-term use only

### FORGET

This command removes information from memory.

```
REMEMBER secretCode = "1234"
FORGET secretCode
```

**Expected Output:**
- Action: Removed variable secretCode from memory
- Result: Variable secretCode is now NULL
- Reasoning: Information has been cleared

### VERIFY

This checks if something is true or false.

```
REMEMBER playerAge = 14
VERIFY playerAge GT 10
```

**Expected Output:**
- Action: Checked if playerAge > 10
- Result: TRUE (14 is greater than 10)
- Reasoning: Comparison evaluated to true

### EVALUATE

This calculates something new based on what the AI knows.

```
REMEMBER length = 5
REMEMBER width = 3
EVALUATE area = length * width
```

**Expected Output:**
- Action: Calculated area using formula length * width
- Result: Variable area = 15
- Reasoning: Multiplication of 5 × 3 = 15

### REPORT

This explains what's happening in a clear way.

```
REMEMBER playerName = "Alex"
REMEMBER playerScore = 95
REPORT "Player {playerName} scored {playerScore} points"
```

**Expected Output:**
- Action: Generated report message
- Result: "Player Alex scored 95 points"
- Reasoning: Successfully formatted message with variable values

## Comparison Operators

These help compare things:

### EQ (Equal to)

```
REMEMBER apples = 5
VERIFY apples EQ 5
```

**Expected Output:**
- Action: Checked if apples equals 5
- Result: TRUE
- Reasoning: 5 is equal to 5

### NEQ (Not Equal to)

```
REMEMBER bananas = 3
VERIFY bananas NEQ 4
```

**Expected Output:**
- Action: Checked if bananas not equal to 4
- Result: TRUE
- Reasoning: 3 is not equal to 4

### GT (Greater Than)

```
REMEMBER score = 85
VERIFY score GT 70
```

**Expected Output:**
- Action: Checked if score is greater than 70
- Result: TRUE
- Reasoning: 85 is greater than 70

### LT (Less Than)

```
REMEMBER temperature = 15
VERIFY temperature LT 20
```

**Expected Output:**
- Action: Checked if temperature is less than 20
- Result: TRUE
- Reasoning: 15 is less than 20

### GTE (Greater Than or Equal to)

```
REMEMBER playerAge = 12
VERIFY playerAge GTE 12
```

**Expected Output:**
- Action: Checked if playerAge is greater than or equal to 12
- Result: TRUE
- Reasoning: 12 is equal to 12

### LTE (Less Than or Equal to)

```
REMEMBER items = 10
VERIFY items LTE 15
```

**Expected Output:**
- Action: Checked if items is less than or equal to 15
- Result: TRUE
- Reasoning: 10 is less than 15

## Control Flow Commands

These help make decisions:

### IF, THEN, ELSE

This is like a fork in the road - if something is true, do one thing; otherwise, do something else.

```
REMEMBER temperature = 32
IF temperature GT 30 THEN
    REPORT "It's hot today!"
ELSE
    REPORT "It's not too hot today."
END IF
```

**Expected Output:**
- Action: Checked if temperature > 30
- Result: TRUE (32 is greater than 30)
- Action: Executed THEN block
- Result: "It's hot today!"
- Reasoning: Temperature condition was true

### CASE

This handles multiple possible situations.

```
REMEMBER weatherType = "rainy"
CASE weatherType
    WHEN "sunny" THEN
        REPORT "Bring sunglasses!"
    WHEN "rainy" THEN
        REPORT "Bring an umbrella!"
    WHEN "snowy" THEN
        REPORT "Wear a warm coat!"
    ELSE
        REPORT "Check the weather forecast."
END CASE
```

**Expected Output:**
- Action: Evaluated weatherType in CASE statement
- Result: Matched "rainy" condition
- Action: Executed matching WHEN block
- Result: "Bring an umbrella!"
- Reasoning: weatherType exactly matched the second condition

## Advanced Commands

### MATCH

This checks if something matches a pattern.

```
REMEMBER email = "alex@example.com"
MATCH email WITH "^[a-z]+@[a-z]+\.[a-z]+$"
```

**Expected Output:**
- Action: Checked if email matches the pattern
- Result: TRUE
- Reasoning: String matches the email pattern

### LIKE

This checks if something contains specific text.

```
REMEMBER message = "Hello, how are you today?"
VERIFY message LIKE "%how are you%"
```

**Expected Output:**
- Action: Checked if message contains "how are you"
- Result: TRUE
- Reasoning: The phrase is found within the message

### IMPLIES

This is for logical reasoning - if one thing is true, another thing must also be true.

```
REMEMBER isRaining = TRUE
REMEMBER isCloudy = TRUE
VERIFY isRaining IMPLIES isCloudy
```

**Expected Output:**
- Action: Checked logical implication
- Result: TRUE
- Reasoning: If it's raining, it must be cloudy

### FILTER

This finds items that match certain conditions.

```
REMEMBER fruits = ["apple", "banana", "cherry", "date"]
FILTER shortFruits = fruits WHERE LENGTH(item) LTE 5
```

**Expected Output:**
- Action: Filtered list based on string length
- Result: shortFruits = ["apple", "date"]
- Reasoning: Only kept fruits with 5 or fewer letters

### SELECT

This picks specific items from a group.

```
REMEMBER students = [
  {"name": "Alex", "score": 92},
  {"name": "Sam", "score": 85},
  {"name": "Jordan", "score": 95}
]
SELECT topStudent = students ORDER BY score DESC LIMIT 1
```

**Expected Output:**
- Action: Selected top student by score
- Result: topStudent = {"name": "Jordan", "score": 95}
- Reasoning: Ordered by score and took the highest one

### COUNT

This counts how many items are in a group.

```
REMEMBER friends = ["Alex", "Jordan", "Sam", "Taylor"]
COUNT totalFriends = friends
```

**Expected Output:**
- Action: Counted elements in the friends array
- Result: totalFriends = 4
- Reasoning: There are 4 items in the array

### SUM

This adds up numbers.

```
REMEMBER scores = [85, 92, 78, 90]
SUM totalScore = scores
```

**Expected Output:**
- Action: Added all numbers in the scores array
- Result: totalScore = 345
- Reasoning: 85 + 92 + 78 + 90 = 345

### EXISTS

This checks if something exists or has a value.

```
REMEMBER playerName = "Alex"
REMEMBER playerAge = NULL
EXISTS nameExists = playerName
EXISTS ageExists = playerAge
```

**Expected Output:**
- Action: Checked if playerName exists and has a value
- Result: nameExists = TRUE
- Action: Checked if playerAge exists and has a value
- Result: ageExists = FALSE
- Reasoning: playerName has a value, but playerAge is NULL

### CONSIDER

This helps think about context or additional information.

```
REMEMBER isRaining = TRUE
CONSIDER umbrellaNeeded = TRUE
CONSIDER raincoatHelpful = TRUE
```

**Expected Output:**
- Action: Added contextual consideration about umbrellas
- Result: Contextual variable umbrellaNeeded = TRUE
- Action: Added contextual consideration about raincoats
- Result: Contextual variable raincoatHelpful = TRUE
- Reasoning: These are relevant considerations given that it's raining

## Complete Example

Here's everything working together:

```
REMEMBER userName = "Alex"
REMEMBER userAge = 12
REMEMBER favoriteGames = ["Chess", "Minecraft", "Basketball"]

VERIFY userAge GTE 8
REPORT "User age verification complete."

COUNT gameCount = favoriteGames
REPORT "User likes {gameCount} games."

IF gameCount GT 2 THEN
    REPORT "{userName} has many game interests!"
ELSE
    REPORT "{userName} has a few favorite games."
END IF

FILTER boardGames = favoriteGames WHERE item EQ "Chess"
EXISTS likesBoardGames = boardGames
REPORT "Likes board games: {likesBoardGames}"

CONSIDER friendlyMessage = "What's your favorite game to play?"

CASE userAge
    WHEN userAge LT 10 THEN
        REPORT "Game recommendations for younger players."
    WHEN userAge GTE 10 AND userAge LT 13 THEN
        REPORT "Game recommendations for intermediate players."
    ELSE
        REPORT "Game recommendations for advanced players."
END CASE

REPORT "Analysis complete for user {userName}."
```

**Expected Output:**
- Action: Set userName to "Alex"
- Result: Variable userName = "Alex"

- Action: Set userAge to 12
- Result: Variable userAge = 12

- Action: Set favoriteGames to array with 3 games
- Result: Variable favoriteGames = ["Chess", "Minecraft", "Basketball"]

- Action: Verified userAge >= 8
- Result: TRUE
- Action: Reported verification message
- Result: "User age verification complete."

- Action: Counted items in favoriteGames
- Result: gameCount = 3
- Action: Reported games count
- Result: "User likes 3 games."

- Action: Checked if gameCount > 2
- Result: TRUE
- Action: Executed THEN branch
- Result: "Alex has many game interests!"

- Action: Filtered for board games
- Result: boardGames = ["Chess"]
- Action: Checked if boardGames exists and has items
- Result: likesBoardGames = TRUE
- Action: Reported board game preference
- Result: "Likes board games: TRUE"

- Action: Added contextual consideration
- Result: friendlyMessage = "What's your favorite game to play?"

- Action: Evaluated userAge in CASE statement
- Result: Matched second condition (age between 10-12)
- Action: Executed matching WHEN block
- Result: "Game recommendations for intermediate players."

- Action: Reported completion message
- Result: "Analysis complete for user Alex."

## Try It Yourself!

Copy any of these examples and try to predict what will happen. Then check if your prediction matches the expected output!

## Terms

**RESULT (RES)**  
Represents the outcome of an evaluation or directive consideration. Can be stored for future reference.

**REMEMBER (REM)**  
Assigns a value or evaluation result to a named variable in state. Essential for creating persistent or temporary memory in AAIL logic.

## Example: Using CONSIDER DIRECTIVE with RES REM

### Directive Definition
Let's assume we have a directive defined as:

directive:
  name: workloadConflictResolution
  description: Identifies conflicts between workload balance and overtime minimization.
  scope: GLOBAL
  logic:
    - IF directiveA IMPLIES increaseWorkload THEN
        - CONSIDER DIRECTIVE directiveB
        - IF directiveB CONFLICTS directiveA THEN
            - REPORT "Conflict detected between workload balance and overtime minimization."

### Main Logic

REMEMBER directiveA = "Maximize team workload balance"
REMEMBER directiveB = "Minimize overtime"

CONSIDER DIRECTIVE workloadConflictResolution RES REM conflictCheckResult

IF conflictCheckResult EQ TRUE THEN
    REPORT "Workload and overtime objectives are in conflict."
ELSE
    REPORT "No conflict detected between workload and overtime objectives."
END IF

### Expected Output
- The system evaluates the workloadConflictResolution directive.
- If a conflict exists, `conflictCheckResult` will be TRUE.
- The appropriate REPORT line will be triggered based on the result.

### Reasoning
- `CONSIDER DIRECTIVE` checks the directive logic without automatic execution.
- `RES REM` stores the evaluation result for later conditional logic.
- This pattern allows transparent meta-reasoning and flexible response logic.

## Eval Block Format Declaration

- **Simple Use:** If the eval block only contains AAIL logic, no format declaration is needed.
- **Complex Use:** If multiple formats are used, declare them in the :start eval line.

Example:
:start eval YAML, Markdown, AAIL

yaml:
  teamSize: 5

Markdown:
  ## Purpose
  Evaluate workload conflicts.

AAIL:
    - IF workload GT capacity THEN
        - REPORT "Overload detected."
:end eval
