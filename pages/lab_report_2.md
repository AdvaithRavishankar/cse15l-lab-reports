# Lab Report 2 - Debugging MarkdownParse
---
## Original File

the original file can be seen below which was forked:

![git1](../images/lab_report_2/git_1.png)

The purpose of this file was to take an input mardown file and output all the links in the file. In general the file worked fun however, there were some bugs and symptoms with the program that was fixed. This lab report will go over three such changes:

## Test 1 - Masked Links

The first issue encountered in the group discussion was the fact that the program would read all characters in the link format. However, these supposed "links" may not acctaually be a link but some characters. Therefore to fix this symptom, a test file was committed:

![test1](../images/lab_report_2/test_1.png)

When the ```MarkdownParse.java``` file was compiled and run, it lead to the following symptom of the word "hi" being intoduced as a link:

![error1](../images/lab_report_2/error_1.png)

To fix this symptom, we added a condition to check whether it was a web link. The if statement checked whether if it contained ```http:// or https://``` as they were needs in web based urls. The committed file change is as shown:

![git2](../images/lab_report_2/git_2.png)

When this was compiled, the bug of the lacking if statement was fixed. This can be seen below when the code was recompiled:

![error_f1](../images/lab_report_2/error_1_fixed.png)

Therefore, the relationship between the bug and the symptom is that the symptom was caused due to a lack of conditional edge testing of the file. The failure inducing input of a supposed "masked link" caused the issue.

## Test 2 - Extra Line Infinite Loop

Another symptom which was encoutered is when the test file had a blank line at the end of it as shown below:

![test2](../images/lab_report_2/test_2.png)

To see what the symptom is, the follwoing changes are needed to the ```MarkdownParse.java``` file:

![git3](../images/lab_report_2/git_3.png)

When this is compiled and run, an infinite loop is encountered:

![error2](../images/lab_report_2/error_2.png)

To fix this issue, the bug in the code needs to be addressed by adding a conditonal check for repeated loops:

![git4](../images/lab_report_2/git_4.png)

When this is rerun, the symptom is now resolved:

![error_f2](../images/lab_report_2/error_2_fixed.png)

Therefore, the relationship between the bug and the symptom is that the symptom was caused due to a lack of conditional edge testing again. The failure inducing input of a blank ending line caused the infinite loop.

## Test 3 - Imgaes as links

In Markdown, the image format is ```![](...)```. This however, does not function as the definitiion of a link. Therefore, to observe this symptom, we use the following test file:

![test3](../images/lab_report_2/test_3.png)

when this is run, the following output is observed:

![error3](../images/lab_report_2/error_3.png)

To fix this, we just need to add another if statment to check if an ```!``` is there to before the ```[``` to address the bug:

![git5](../images/lab_report_2/git_5.png)

When this is rerun, 

![error_f3](../images/lab_report_2/error_3_fixed.png)

The image link no longer appaers. 

Therefore, the relationship between the bug and the symptom is that the symptom was caused due to a lack of conditional edge testing again. The failure inducing input of a ! caused an incorrect program behaviour.

THIS IS THE END OF THE LAB REPORT

