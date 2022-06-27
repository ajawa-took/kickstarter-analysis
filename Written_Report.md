# Kickstarting with Excel



## Overview of Project


 We looked at the data from past theater kickstarters.


### Purpose

 To identify factors, such as launch date or fundraising goal, that predict the success of the kickstarter.



## Analysis and Challenges



### Analysis of Outcomes Based on Launch Date

 Created a pivot table of "launch month" vs "outcome" from all data, filtered by "parent category" to include only "theater" projects, then created a line graph from that table; both are in the sheet "Theater Outcomes by Launch Date". Initial data was first transformed to convert unix data stamps into excel dates; and to separate "category" into "parent category" and "subcategory".
 
 ===>>> images and links to code



### Analysis of Outcomes Based on Goals


 Obtained counts of "theater/plays" projects with each possible outcome for each of the given goal ranges. Converted counts to percentages of all projects in the given goal range. Created a line graph of these percentages as a function of the goal range. The work is in the "Outcomes based on Goals" sheet. Auxillary data is stored in row 41 and column N, to keep the top left of the sheet pretty.

 The conditions in the elaborate COUNTIFS formula that generates values in the range (B2:D13), example for cell B2:
		Sheet1!$D$2:$D$4115, ">="&$N1,
sets the bottom of the Goal range bucket for the row
		Sheet1!$D$2:$D$4115, "<"&$N2,
sets the top of the Goal range bucket for the row
		Sheet1!$F$2:$F$4115, B$41,
sets the Outcome for the column
		Sheet1!$O$2:$O$4115, "plays"
sets the Subcategory for everything.

 ===>>> images and links to code

### Challenges and Difficulties Encountered



 Problem: dates were not readable.
 Solution: the magic excel formula  =(((X/60)/60/24)+DATE(1970,1,1)) converts unix timestamps into excel dates.

 Problem: pivot chart has ugly grey rectangles for filtering the pivot table.
 Solution: crop the top to remove most of these, use eraser tool in paint to remove the last one.

 Problem: not enough theater/plays projects with high goals.
 Solution 1: group together all projects with goals over $25,000.
 Solution 2: analyze a wider class of projects, such as all theater projects.
 (Solutions contradict specifications, so not implemented.)

## Results



### Launch your theater kickstarter in May, not in December!

 Many more theater kickstarters are launched in spring and summer than in fall and winter. The number of failed projects just barely show this trend, but the number of successful projects doubles from winter to early summer. May appears to be the best month to launch a theater kickstarter, with two thirds of the projects succeeding; while December is the worst, with only half the projects funded.

### For kickstarting plays, smaller goals = more success.

 Among kickstarters with goals under $25,000, smaller campaigns were clearly more successful. At the high end of that range, only about half of the projects were funded; but at the low end, nearly three-quarters were funded.

  The wild swings in the right half of the graph are the result of very sparse data. Many of those goal ranges contain less than 10 projects. Nevertheless, it is worth noting that barely over a quarter of these 42 large (goal over $25,000) projects were funded, maintaining the trend found among smaller projects.

### Concerns

 This dataset is very outdated: the latest project launch date is in March 2017. Kickstarter is a quite a recent thing, so it is likely to have changed a lot. The theater world has also changed hugely in the last two years.


### Further directions

 Length of campaign and number of backers are two other interesting factors to investigate. Since Louise can set the deadline for the kickstarter, optimal campaign length is a directly actionable piece of information. Knowing how many backers it usually takes to reach the goal would help Louise decide to target her advertizing more widely or more narrowly.


