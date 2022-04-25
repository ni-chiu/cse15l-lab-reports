# CSE15L Lab Report 2 (Week 4)

This blog post is written as Lab Report 2 for CSE15L. Here, I will discuss three code changes my lab partner and I made while debugging our code in
our Week 3 Lab.

## Code Change 1: Characters After Final Close Parenthesis

### Code Change Diff From Github
![Code Diff 1](images\Code_Diff1.png)

### Failure-Inducing Test File
[Link to the test file which caused the bug](https://github.com/ni-chiu/markdown-parser/blob/main/test-file.md)

### Symptom of Failure-Inducing Input
![Symptom 1](images\TerminalMsg1.png)

### Relationship Between the Bug, Symptom, and Failure-Inducing Input
 The test file was a failure-inducing input because it contained a space after the final parenthesis of the last link. Since the space is counted as a character, it increases the length of the test file. The code relies on a while loop to break; however, the break condition cannot be satisfied because currentIndex can never be greater than or equal to mardown.length if the final close parenthesis is not the final character of the file. As a result, running the file produces an infinite loop and results in an `OutofMemoryError` error.

## Code Change 2: Missing Parenthesis

### Code Change Diff From Github
![Code Diff 2](images\Code_Diff2.png)

### Failure-Inducing Test File
[Link to the test file which caused the bug](https://github.com/ni-chiu/markdown-parser/blob/main/test-file2.md)

### Symptom of Failure-Inducing Input
![Symptom 2](images\Symptom2.png)

### Relationship Between the Bug, Symptom, and Failure-Inducing Input
The test file was a failure-inducing input because it contained missing parenthesis. The code relies on the presence of both open and close parenthesis to be able to determine where the links start and end and what the contents within the parenthesis are. When running the code with the failure-inducing input, the index of the parenthesis are set to `-1` since they are not present, which results in an `IndexOutOfBoundsException` error because `-1` is not a valid index.

## Code Change 3: Missing Brackets

### Code Change Diff From Github

![Code Diff 3](images\Code_Diff3.png)

### Failure-Inducing Test File
[Link to the test file which caused the bug](https://github.com/ni-chiu/markdown-parser/blob/main/test-file3.md)

### Symptom of Failure-Inducing Input
![Symptom 3](images\Symptom3.png)

### Relationship Between the Bug, Symptom, and Failure-Inducing Input
The test file was a failure-inducing input because it was missing the close brackets for the link. Although the initial change fixed the edge case of a missing open bracket, a missing close bracket still broke the code because the value of `currentIndex` relied on an invalid `closeBracket` value of `-1`. The invalid `closeBracket` value meant that once again, the while loop condition `while(currentIndex < markdown.length())` could never be satisfied, resulting in an infinite while loop.

## End
Thank you for reading!