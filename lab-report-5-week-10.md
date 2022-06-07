# CSE15L Lab Report 5 (Week 10)

## How I Found the Tests with Different Results
To find tests with differing results, I used vimdiff on the results of running a bash script. Vimdiff allowed me to
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
The Bug: The bug in the code in my implementation occurs on line 42. The code does not properly consider the possiblity of having nested parenthesis as part of the link URL. Currently, the add statement adds everything in between the open parenthesis and next close parenthesis, but in reality, it should pair the parenthesis and return everything within the outside parenthesis.

Screenshot of the Code:
![Screenshot of Code 2](images\errorCodeTest495.png)

## Test 2:

### Link to Test File
[Link to Test 2](https://github.com/nidhidhamnani/markdown-parser/blob/main/test-files/505.md)

### Which Implementation (or neither) is Correct?
Based on the expected result and the actual results, I think neither implementation is incorrect.

### Expected and Actual Output
Code in markdown:

![test505](images\test505md.png)

Based on the markdown code and the preview in VSCode, I believe that the expected output should be either `[title ""]` or `[url]`.

It is completely different than what I thought it would be and I am not completely sure that is the expected output. It appears that the `/url` in the markdown file is affecting how programs are perceiving the link and its path.

Actual output from my implementation:
![Actual Output myRepo](images\Test505myRepo.png)

Actual output from the provided implementation:
![Actual Output providedRepo](images\Test495theirRepo.png)

### Describing the Bug for the Incorrect Implementation that’s not correct. What is Wrong and Where?
The Bug: Since both implementation are incorrect, the code that is being reviewed is the provided implementation. The bug in the code is between lines 75 and 80. The if statement does not add anything into `toReturn` because the index of a space is not negative 1. However, as the markdown previews show, although the link is invalid, it is still recognized as a link meaning something should be added to `toReturn`.

Screenshot of the Code:
![Screenshot of Code 2](images\errorCodeTest505.png)