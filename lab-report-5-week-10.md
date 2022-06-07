# CSE15L Lab Report 5 (Week 10)

## How I Found the Tests with Different Results
To find tests with differing results, I used vimdiff. Vimdiff allowed me to
easily find the different outputs since it highlights the differences.

## Test 1:

### Link to Test File
[Link to Test 1 - Test #495](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/495.md)

### Which Implementation (or neither) is Correct?
The implementation in the provided repository is the correct implementation based
on the outputs of the test.

### Expected and Actual Output
Expected Output: `[foo(and(bar))]`

Actual output from my implementation:
![Actual Output myRepo](images\Test495myRepo.png)

Actual output from the provided implementation:
![Actual Output providedRepo](images\Test495theirRepo.png)

### Describing the Bug for the Incorrect Implementation that’s not correct. What is Wrong and Where?
The Bug: The bug in the code in my implementation occurs on line 42. The code does not properly consider the possiblity of having parenthesis as part of the link URL. Currently, the add statement adds everything in between the open parenthesis and next close parenthesis, but in reality, it should pair the parenthesis and return everything within the outside parenthesis.

Screenshot of the Code:
![Screenshot of Code 2](images\errorCodeTest495.png)

## Test 2:

### Link to Test File
[Link to Test 2]()

### Which Implementation (or neither) is Correct?


### Expected and Actual Output
![Expected Output]()

Actual output from my implementation:
![Actual Output myRepo]()

Actual output from the provided implementation:
![Actual Output providedRepo]()

### Describing the Bug for the Incorrect Implementation that’s not correct. What is Wrong and Where?
The Bug:

Screenshot of the Code:
![Screenshot of Code 2]()