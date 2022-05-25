# CSE15L Lab Report 4 (Week 8)

This is the lab report for week 8. This lab report will cover testing of
snippets of text in my original markdown-parse repo and the repo that was
reviewed in the week 7 lab.

## Link to the `markdown-parse` Repositories

[My repository link](https://github.com/ni-chiu/markdown-parser-nichiu)

For this lab report, I made a copy of the repository that was reviewed in week 7 so I could
properly save the markdown files and changes I made to the test file.

[Repository that was reviewed in week 7](https://github.com/richmass1/markdown-parser)

[Copy of the above repo](https://github.com/ni-chiu/markdown-parse-inclassreview)

## Testing the New Code Snippets

### Snippet 1

#### Deciding on what the snippet should produce
Using the [CommonMark demo site](https://spec.commonmark.org/dingus/) to determine expected output, 
the output should be: ``[`google.com, google.com, ucsd.edu]``


#### Code

The tests are the same for the two repositories.

![Snippet1Test](images\myRepoTest1.png)

#### Corresponding Output

My Repo:

![myRepoTestOutput1](images\myRepoOutput1.png)

Reviewed Repo:

![reviewRepoTestOutput1](images\reviewRepoOutput1.png)

#### Do you think there is a small code change that will make your program work for snippet 1 and all related cases that use inline code with backticks?

Based on the expected output and the test failure, I believe there is a small code change that will make my program
work for snippet 1 and all related cases that use inline code with backticks. There are some cases where backticks are fine, like when the backticks are both within the open and close bracket/parenthesis. However, problems arise when
the backticks encompase a bracket/parenthesis that is required for the link to the recognized as a link. Therefore, the code change would insure that key brackets and/or parenthesis within backticks are ignored so it does not get recognized as part of a link when it is actually inline code. 

### Snipet 2

#### Deciding on what the snippet should produce
The output should be: ``[a.com, a.com(()), example.com]``

#### Code

The tests are the same for the two repositories.

![Snippet2Test](images\myRepoTest2.png)

#### Corresponding Output

My Repo:

![myRepoTestOutput2](images\myRepoOutput2.png)

Reviewed Repo:

![reviewRepoTestOutput2](images\reviewRepoOutput2.png)

#### Do you think there is a small code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets?

Because `markdown-parser` uses open and close brackets/parenthesis as the key to recognizing what is a link and what is not, I believe the necessary change would not be a small one. The code would have to pair an open bracket/parenthesis
with the appropriate close bracket/parenthesis rather than the next one that is encountered. The discrepancy between expected output and actual output indicates that the code is unable to do so, which is why there are random unpaired brackets and/or parenthesis in the test output.

### Snipet 3

#### Deciding on what the snippet should produce
The output should be: ``[https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]``

#### Code

The tests are the same for the two repositories.

![Snippet3Test](images\myRepoTest3.png)

#### Corresponding Output

My Repo:

![myRepoTestOutput3](images\myRepoOutput3.png)

Reviewed Repo:

![reviewRepoTestOutput3](images\reviewRepoOutput3.png)

#### Do you think there is a small code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses?

The expected output on the markdown demo site shows that links that take up multiple lines and links with newlines within the brackets and parenthesis should not be recognized as a link; however, the current code does recognize then as links which causes the test to fail. I do not know what the actual code for this change would be and I do not think this change is a small code change, but a fix for this problem would be to have the markdown parser ignore any links who has any parenthesis or brackets on different lines in the text file. That would insure that links with newlines are not recognized as valid links even if they have open and close brackets/parenthesis.