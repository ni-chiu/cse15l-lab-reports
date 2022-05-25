# CSE15L Lab Report 4 (Week 8)

This is the lab report for week 8. This lab report will cover testing of
snippets of text in my original markdown-parse repo and the repo that was
reviewed in the week 7 lab.

## Link to the `markdown-parse` Repositories

[My repository link](https://github.com/ni-chiu/markdown-parser-nichiu)

[Repository that was reviewed in week 7](https://github.com/richmass1/markdown-parser)

## Testing the New Code Snippets

### Snippet 1

#### Deciding on what the snippet should produce
Using the [CommonMark demo site](https://spec.commonmark.org/dingus/) to determine expected output, 
the output should be: ``[`google.com, google.com, ucsd.edu]``


#### Code

The tests are the same for the two repositories.

![Snippet1Test](images\myRepoTest1.png)

#### Corresponding Output
*Insert image of the junit test results*

My Repo:

Reviewed Repo:

*Insert image of the junit test results*

#### Do you think there is a small code change that will make your program work for snippet 1 and all related cases that use inline code with backticks?

*Answer question*

### Snipet 2

#### Deciding on what the snippet should produce
The output should be: ``[a.com, a.com(()), example.com]``

#### Code

The tests are the same for the two repositories.

![Snippet2Test](images\myRepoTest2.png)

#### Corresponding Output
*Insert image of the junit test results*

My Repo:

Reviewed Repo:

#### Do you think there is a small code change that will make your program work for snippet 2 and all related cases that nest parentheses, brackets, and escaped brackets?

*Answer question*

### Snipet 3

#### Deciding on what the snippet should produce
The output should be: ``[https://sites.google.com/eng.ucsd.edu/cse-15l-spring-2022/schedule]``

#### Code

The tests are the same for the two repositories.

![Snippet3Test](images\myRepoTest3.png)

#### Corresponding Output
*Insert image of the junit test results*

My Repo:

Reviewed Repo:

#### Do you think there is a small code change that will make your program work for snippet 3 and all related cases that have newlines in brackets and parentheses?

*Answer question*